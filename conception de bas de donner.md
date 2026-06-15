

Conception de la base de données — PaymentModule
USERS
Colonne	Type	Contrainte
id	INT	PK, AUTO_INCREMENT
uuid	VARCHAR(36)	UNIQUE, NOT NULL
name	VARCHAR(100)	NOT NULL
email	VARCHAR(150)	UNIQUE, NOT NULL
password	VARCHAR(255)	NOT NULL (bcrypt)
role	ENUM	'user','admin' DEFAULT 'user'
created_at	TIMESTAMP	DEFAULT CURRENT_TIMESTAMP
PLANS
id	INT	PK, AUTO_INCREMENT
uuid	VARCHAR(36)	UNIQUE, NOT NULL
name	VARCHAR(100)	NOT NULL
price_monthly	DECIMAL(10,2)	NOT NULL
price_yearly	DECIMAL(10,2)	NOT NULL
features	JSON	NULL
is_active	TINYINT(1)	DEFAULT 1
SUBSCRIPTIONS
id	INT	PK, AUTO_INCREMENT
uuid	VARCHAR(36)	UNIQUE, NOT NULL
user_id	INT	FK → users(id)
plan_id	INT	FK → plans(id)
cycle	ENUM	'monthly','yearly'
status	ENUM	'active','cancelled','expired'
start_date	DATE	NOT NULL
end_date	DATE	NULL
TRANSACTIONS
id	INT	PK, AUTO_INCREMENT
uuid	VARCHAR(36)	UNIQUE, NOT NULL
user_id	INT	FK → users(id)
plan_id	INT	FK → plans(id)
coupon_id	INT	FK → coupons(id), NULL
amount	DECIMAL(10,2)	NOT NULL
tax_amount	DECIMAL(10,2)	DEFAULT 0
discount_amount	DECIMAL(10,2)	DEFAULT 0
currency	VARCHAR(3)	DEFAULT 'USD'
status	ENUM	'pending','completed','failed','refunded'
provider	VARCHAR(50)	'stripe','paypal'
created_at	TIMESTAMP	DEFAULT CURRENT_TIMESTAMP
INVOICES
id	PK
transaction_id	FK → transactions
user_id	FK → users
amount	DECIMAL(10,2)
tax_amount	DECIMAL(10,2)
status	ENUM
issued_at	TIMESTAMP
COUPONS
id	PK
code	VARCHAR(50) UNIQUE
discount_type	'percent','fixed'
discount_value	DECIMAL(10,2)
max_uses	INT
used_count	INT DEFAULT 0
is_active	TINYINT(1)
expires_at	TIMESTAMP NULL
REFUNDS
id	INT	PK, AUTO_INCREMENT
transaction_id	INT	FK → transactions(id)
amount	DECIMAL(10,2)	NOT NULL
reason	TEXT	NULL
status	ENUM	'pending','completed','failed'
created_at	TIMESTAMP	DEFAULT CURRENT_TIMESTAMP
■ Clé primaire (PK)
■ Clé étrangère (FK)
