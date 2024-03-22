# DBMS_Project_Group-4
SQL- Project on Stock Brokerage Management System
CREATE TABLE symbol_parthiv (
    symbol_id SERIAL PRIMARY KEY,
    symbol_name VARCHAR(50) UNIQUE
);


INSERT INTO symbol_parthiv (symbol_name) VALUES 
('TCS'),
('INFY'),
('RELIANCE'),
('HDFC'),
('ICICIBANK'),
('HINDUNILVR'),
('ITC'),
('ONGC'),
('SBIN'),
('BAJFINANCE'),
('TATASTEEL'),
('WIPRO'),
('AXISBANK'),
('SUNPHARMA'),
('HDFCBANK'),
('LT'),
('INDUSINDBK'),
('COALINDIA'),
('MARUTI'),
('KOTAKBANK');


CREATE TABLE company_name_parthiv (
    company_id SERIAL PRIMARY KEY,
    symbol_id INT,
    company_name VARCHAR(100),
    FOREIGN KEY (symbol_id) REFERENCES symbol(symbol_id)
);


INSERT INTO company_name_parthiv (symbol_id, company_name) VALUES 
(1, 'Tata Consultancy Services'),
(2, 'Infosys'),
(3, 'Reliance Industries'),
(4, 'Housing Development Finance Corporation'),
(5, 'ICICI Bank'),
(6, 'Hindustan Unilever'),
(7, 'ITC Limited'),
(8, 'Oil and Natural Gas Corporation'),
(9, 'State Bank of India'),
(10, 'Bajaj Finance'),
(11, 'Tata Steel'),
(12, 'Wipro'),
(13, 'Axis Bank'),
(14, 'Sun Pharmaceutical Industries'),
(15, 'HDFC Bank'),
(16, 'Larsen & Toubro'),
(17, 'IndusInd Bank'),
(18, 'Coal India'),
(19, 'Maruti Suzuki India'),
(20, 'Kotak Mahindra Bank');


CREATE TABLE stock_price_parthiv (
    price_id SERIAL PRIMARY KEY,
    symbol_id INT,
    price DECIMAL(10,2),
    FOREIGN KEY (symbol_id) REFERENCES symbol(symbol_id)
);


INSERT INTO stock_price_parthiv (symbol_id, price) VALUES 
(1, 3500.00),
(2, 1800.50),
(3, 2500.75),
(4, 2800.25),
(5, 650.80),
(6, 2200.00),
(7, 210.45),
(8, 120.30),
(9, 400.90),
(10, 4800.20),
(11, 900.60),
(12, 450.75),
(13, 700.35),
(14, 520.90),
(15, 1500.25),
(16, 1800.50),
(17, 450.75),
(18, 180.25),
(19, 6000.00),
(20, 2200.75);


CREATE TABLE market_cap_kirtan (
    cap_id SERIAL PRIMARY KEY,
    symbol_id INT,
    market_cap DECIMAL(20,2),
    FOREIGN KEY (symbol_id) REFERENCES symbol(symbol_id)
);


INSERT INTO market_cap_kirtan (symbol_id, market_cap) VALUES 
(1, 2000000000000.00),
(2, 1500000000000.00),
(3, 3000000000000.00),
(4, 2500000000000.00),
(5, 800000000000.00),
(6, 1200000000000.00),
(7, 700000000000.00),
(8, 400000000000.00),
(9, 1000000000000.00),
(10, 1800000000000.00),
(11, 500000000000.00),
(12, 600000000000.00),
(13, 900000000000.00),
(14, 700000000000.00),
(15, 1300000000000.00),
(16, 1500000000000.00),
(17, 550000000000.00),
(18, 200000000000.00),
(19, 2000000000000.00),
(20, 1000000000000.00);



CREATE TABLE sector_kirtan (
    sector_id SERIAL PRIMARY KEY,
    sector_name VARCHAR(100) UNIQUE
);


INSERT INTO sector_kirtan (sector_name) VALUES 
('Information Technology'),
('Oil & Gas'),
('Banking & Financial Services'),
('FMCG'),
('Pharmaceutical'),
('Automobile'),
('Metals & Mining'),
('Telecommunication'),
('Retail'),
('Healthcare'),
('Real Estate'),
('Utilities'),
('Consumer Electronics'),
('Entertainment'),
('Aerospace'),
('Defense'),
('Hospitality'),
('Education'),
('Logistics'),
('Insurance');


CREATE TABLE dividend_yield_kirtan (
    yield_id SERIAL PRIMARY KEY,
    symbol_id INT,
    dividend_yield DECIMAL(5,2),
    FOREIGN KEY (symbol_id) REFERENCES symbol(symbol_id)
);


INSERT INTO dividend_yield_kirtan (symbol_id, dividend_yield) VALUES 
(1, 1.50),
(2, 1.80),
(3, 2.25),
(4, 1.20),
(5, 1.75),
(6, 2.10),
(7, 1.30),
(8, 0.80),
(9, 1.90),
(10, 0.75),
(11, 1.60),
(12, 1.85),
(13, 1.95),
(14, 2.05),
(15, 1.40),
(16, 1.70),
(17, 1.65),
(18, 2.20),
(19, 0.90),
(20, 1.15);


CREATE TABLE eps_siddhi (
    eps_id SERIAL PRIMARY KEY,
    symbol_id INT,
    earnings_per_share DECIMAL(10,2),
    FOREIGN KEY (symbol_id) REFERENCES symbol(symbol_id)
);


INSERT INTO eps_siddhi(symbol_id, earnings_per_share) VALUES 
(1, 150.25),
(2, 90.50),
(3, 120.75),
(4, 80.30),
(5, 45.80),
(6, 60.25),
(7, 35.40),
(8, 20.90),
(9, 55.60),
(10, 70.20),
(11, 30.75),
(12, 40.60),
(13, 65.90),
(14, 50.30),
(15, 95.80),
(16, 110.25),
(17, 75.40),
(18, 15.90),
(19, 180.20),
(20, 85.75);


CREATE TABLE volume_siddhi (
    volume_id SERIAL PRIMARY KEY,
    symbol_id INT,
    volume INT,
    FOREIGN KEY (symbol_id) REFERENCES symbol(symbol_id)
);


INSERT INTO volume_siddhi (symbol_id, volume) VALUES 
(1, 1000000),
(2, 1500000),
(3, 2000000),
(4, 800000),
(5, 1200000),
(6, 600000),
(7, 700000),
(8, 500000),
(9, 900000),
(10, 1100000),
(11, 300000),
(12, 400000),
(13, 700000),
(14, 550000),
(15, 950000),
(16, 1200000),
(17, 650000),
(18, 180000),
(19, 800000),
(20, 1000000);


CREATE TABLE pe_ratio_siddhi (
    pe_id SERIAL PRIMARY KEY,
    symbol_id INT,
    pe_ratio DECIMAL(10,2),
    FOREIGN KEY (symbol_id) REFERENCES symbol(symbol_id)
);


INSERT INTO pe_ratio_siddhi (symbol_id, pe_ratio) VALUES 
(1, 25.43),
(2, 28.17),
(3, 20.91),
(4, 33.76),
(5, 18.62),
(6, 29.80),
(7, 24.09),
(8, 15.78),
(9, 22.34),
(10, 35.62),
(11, 19.37),
(12, 27.80),
(13, 30.05),
(14, 23.91),
(15, 26.55),
(16, 21.82),
(17, 31.45),
(18, 17.23),
(19, 24.67),
(20, 29.11);


CREATE TABLE week52_avg_price_siddhi (
    avg_price_id SERIAL PRIMARY KEY,
    symbol_id INT,
    avg_price DECIMAL(10,2),
    FOREIGN KEY (symbol_id) REFERENCES symbol(symbol_id)
);


INSERT INTO week52_avg_price_siddhi (symbol_id, avg_price) VALUES 
(1, 3250.00),
(2, 1700.25),
(3, 2450.50),
(4, 2750.75),
(5, 625.40),
(6, 2150.00),
(7, 200.35),
(8, 110.20),
(9, 380.90),
(10, 4600.10),
(11, 875.60),
(12, 430.75),
(13, 670.35),
(14, 500.90),
(15, 1450.25),
(16, 1750.50),
(17, 425.75),
(18, 170.25),
(19, 5900.00),
(20, 2100.75);


Select*from volume_siddhi;
Select*from eps_siddhi;
Select*from dividend_yield_kirtan;
Select*from company_name_parthiv;
Select*from sector_kirtan;
Select*from market_cap_kirtan;
Select*from stock_price_parthiv;
Select*from symbol_parthiv;
Select*from pe_ratio_siddhi;
Select*from week52_avg_price_siddhi;


SELECT * FROM stock_price_parthiv WHERE symbol_id = 1;

SELECT * FROM company_name_parthiv
JOIN sector_kirtan ON company_name_parthiv.company_id = sector_kirtan.sector_id
WHERE sector_kirtan.sector_name = 'Information Technology';

SELECT * FROM company_name_parthiv WHERE company_name LIKE '%an%';

SELECT company_name, SUM(price) AS total_stock_price
FROM company_name_parthiv
JOIN stock_price_parthiv ON company_name_parthiv.symbol_id = stock_price_parthiv.symbol_id
GROUP BY company_name;

UPDATE stock_price_parthiv
SET price = 3600.00
WHERE symbol_id = (1);
select * FROM stock_price_parthiv;


SELECT * FROM stock_price_parthiv
WHERE price BETWEEN 2500 AND 3000;


DELETE FROM pe_ratio_siddhi
WHERE symbol_id = (1);
select * FROM pe_ratio_siddhi;

