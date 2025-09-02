-- SELECT * FROM sqlProject.zepto;

drop table if exists sqlproject.zepto;

 create table sqlproject.zepto (
 sku_id SERIAL PRIMARY KEY,
 ï»¿Category VARCHAR(120),
 name VARCHAR(150) NOT NULL,
 mrp NUMERIC(8,2),
 discountPercent NUMERIC(5,2),
 availableQuantity INTEGER,
 discountedSellingPrice NUMERIC(8,2),
 weightInGms INTEGER,
 outOfStock BOOLEAN,	
 quantity INTEGER
);

-- --data exploration

-- --count of rows
select count(name) from sqlproject.zepto;

-- --sample data
SELECT * FROM sqlproject.zepto
LIMIT 10;

-- null values
SELECT * FROM sqlproject.zepto
WHERE name IS NULL
OR
ï»¿Category IS NULL
OR
mrp IS NULL
OR
discountPercent IS NULL
OR
discountedSellingPrice IS NULL
OR
weightInGms IS NULL
OR
availableQuantity IS NULL
OR
outOfStock IS NULL
OR
quantity IS NULL;

-- different product categories
SELECT DISTINCT ï»¿Category
FROM sqlproject.zepto
ORDER BY ï»¿Category;

-- products in stock vs out of stock
SELECT outOfStock, COUNT(quantity)
FROM sqlproject.zepto
GROUP BY outOfStock;

-- product names present multiple times
SELECT name, COUNT(quantity) AS "Number of SKUs"
FROM sqlproject.zepto
GROUP BY name
HAVING count(quantity) > 1
ORDER BY count(quantity) DESC;

-- data cleaning

-- products with price = 0
SELECT * FROM sqlproject.zepto
WHERE mrp = 0 OR discountedSellingPrice = 0;

DELETE FROM sqlproject.zepto
WHERE mrp = 0;

-- convert paise to rupees
UPDATE sqlproject.zepto
SET mrp = mrp / 100.0,
discountedSellingPrice = discountedSellingPrice / 100.0;

SELECT mrp, discountedSellingPrice FROM sqlproject.zepto;
