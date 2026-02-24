# Sql-cleaning-project- (Data Analyst)
## queries in sql to cleaning purpose 

create database clean;

use clean;

select * from swiggy
order by sale_id;

set sql_safe_updates=0;

UPDATE swiggy SET Customer_Name = TRIM(Customer_Name);

UPDATE swiggy SET Region = TRIM(Region);

UPDATE swiggy SET Product_Name = TRIM(Product_Name);

UPDATE swiggy SET Payment_Method = TRIM(Payment_Method);

UPDATE swiggy SET Delivery_Status = TRIM(Delivery_Status);

UPDATE swiggy SET City = TRIM(City);

UPDATE swiggy SET order_date = TRIM(order_date);




select * from swiggy;

ALTER TABLE swiggy ADD COLUMN order_date_clean DATE;

alter table swiggy modify column order_date date;
describe swiggy;

update swiggy set
order_date=date_format(str_date(order_date,'%m/%d/%y'),'%y-%m-%d');


UPDATE swiggy SET customer_name = TRIM(customer_name);
set sql_safe_updates=0;
update swiggy set city=trim(city);

select * from swiggy;

UPDATE swiggy SET region = lower(TRIM(region));
commit;
UPDATE swiggy SET product_name = TRIM(product_name);

UPDATE swiggy
SET quantity = CASE
WHEN quantity='one' THEN '1'
WHEN quantity='two' THEN '2'
WHEN quantity='three' THEN '3'
ELSE quantity END;

ALTER TABLE swiggy MODIFY quantity INT;

UPDATE swiggy SET unit_price = ABS(unit_price);

UPDATE swiggy SET total_amount = quantity * unit_price;

UPDATE swiggy SET payment_method='Cash'
WHERE payment_method IN ('cahs','cash');

UPDATE swiggy SET delivery_status='Delivered'
WHERE delivery_status IN ('delivereed','delivered');

ALTER TABLE swiggy DROP COLUMN MyUnknownColumn;

UPDATE swiggy SET city='Hyderabad'
WHERE UPPER(city) LIKE 'HYD%';

UPDATE swiggy SET pincode='500000'
WHERE pincode IS NULL;

ALTER TABLE swiggy MODIFY pincode INT;

select * from swiggy;

select *,
case
when quantity=129 then '1'
when quantity=130 then '1'
when quantity=131 then '1'
else 'no discount'
end as e
 from swiggy;


UPDATE swiggy
SET Quantity = 1
WHERE Sale_id = 122;
update swiggy
set payment_method='Debit'
where sale_id=85;
select * from swiggy 
order by sale_id;
set sql_safe_updates=0;
update swiggy set Delivery_Status="Delivered" where sale_id=18;

UPDATE swiggy
SET quantity = CASE
    WHEN Sale_id = 129 THEN 1
    WHEN sale_id = 130 THEN 1
    WHEN sale_id = 131 THEN 2
    when sale_id = 136 then 2
    when sale_id = 141 then 1
    when sale_id = 146 then 1
    when sale_id = 147 then 1
    when sale_id = 151 then 1
    when sale_id = 154 then 1
    when sale_id = 155 then 1
    when sale_id = 167 then 2
    when sale_id = 169 then 2
    when sale_id = 171 then 1
    when sale_id = 174 then 1
    when sale_id = 177 then 1
    when sale_id= 178 then 2
    when sale_id =182 then 2
    when sale_id =186 then 1
    when sale_id=187 then 1
    when sale_id=189 then 1
    when sale_id=193 then 2
    when sale_id=198 then 1
END
WHERE sale_id IN (129,130,131,136,141,146,147,151,154,155,167,169,171,174,177,178,182,186,187,189,193,198);

update swiggy 
set delivery_status=case
   when sale_id=5 then 'delivered'
   when sale_id =7 then 'Delivered'
   when sale_id=6 then 'delivered'
   when sale_id=11 then 'delivered'
   when sale_id =17 then 'Delivered'
    when sale_id=18 then 'delivered'
   when sale_id =14 then 'Delivered'
   when sale_id =19 then 'Delivered'
   when sale_id =25 then 'Delivered'
   when sale_id =41 then 'Delivered'
   when sale_id =42 then 'Delivered'
   when sale_id =43 then 'Delivered'
   when sale_id =46 then 'Delivered'
   when sale_id =54 then 'Delivered'
   when sale_id =62 then 'Delivered'
   when sale_id =68 then 'Delivered'
   when sale_id =72 then 'Delivered'
   when sale_id =74 then 'Delivered'
   when sale_id =93 then 'Delivered'
   when sale_id =100 then 'Delivered'
   when sale_id =107 then 'Delivered'
   when sale_id =122 then 'Delivered'
   when sale_id =113 then 'Delivered'
   when sale_id =126 then 'Delivered'
   when sale_id =136 then 'Delivered'
   when sale_id =147 then 'Delivered'
   when sale_id =148 then 'Delivered'
   when sale_id =154 then 'Delivered'
   when sale_id =157 then 'Delivered'
   when sale_id =163 then 'Delivered'
   when sale_id =172 then 'Delivered'
   when sale_id =181 then 'Delivered'
   when sale_id =188 then 'Delivered'
   when sale_id =198 then 'Delivered'
end
where sale_id in (5,6,7,11,17,14,18,19,25,41,43,42,46,54,62,68,72,93,100,107,113,122,126,136,147,148,154,157,163,172,181,188,198);



UPDATE swiggy
SET unit_price = unit_price * 0.5;

update swiggy
set payment_method =case
    when sale_id =3 then 'Debit'
	when sale_id =7 then 'Debit'
    when sale_id =9 then 'Debit'
    when sale_id =12 then 'Cash'
    when sale_id =7 then 'Debit'
    when sale_id =20 then 'Debit'
    when sale_id =22 then 'Debit'
    when sale_id =26 then 'Debit'
    when sale_id =27 then 'Debit'
    when sale_id =32 then 'Cash'
    when sale_id =34 then 'Debit'
    when sale_id =36 then 'Debit'
    when sale_id =41 then 'Cash'
    when sale_id =45 then 'Cash'
    when sale_id =50 then 'Debit'
    when sale_id =53 then 'Cash'
    when sale_id =58 then 'Cash'
    when sale_id =59 then 'Cash'
    when sale_id =61 then 'Debit'
    when sale_id =68 then 'Debit'
    when sale_id =70 then 'Debit'
    when sale_id =75 then 'Cash'
    when sale_id =77 then 'Debit'
    when sale_id =80 then 'Cash'
    when sale_id =81 then 'Cash'
    when sale_id =83 then 'Debit'
    when sale_id =85 then 'Debit'
    when sale_id =88 then 'Debit'
    when sale_id =94 then 'Debit'
    when sale_id =97 then 'Cash'
    when sale_id =99 then 'Debit'
    when sale_id =107 then 'Debit'
    when sale_id =108 then 'Cash'
    when sale_id =110 then 'Debit'
    when sale_id =113 then 'Debit'
    when sale_id =114 then 'Debit'
    when sale_id =116 then 'Cash'
    when sale_id =118 then 'Debit'
    when sale_id =119 then 'Debit'
    when sale_id =121 then 'Cash'
    when sale_id =123 then 'Cash'
    when sale_id =129 then 'Debit'
    when sale_id =131 then 'Cash'
    when sale_id =132 then 'Debit'
    when sale_id =135 then 'Debit'
    when sale_id =139 then 'Debit'
    when sale_id =141 then 'Debit'
    when sale_id =142 then 'Cash'
    when sale_id =144 then 'Debit'
    when sale_id =146 then 'Cash'
    when sale_id =147 then 'Debit'
    when sale_id =148 then 'Cash'
    when sale_id =148 then 'Cash'
    when sale_id =151 then 'Debit'
    when sale_id =154 then 'Cash'
    when sale_id =155 then 'Cash'
    when sale_id =161 then 'Cash'
    when sale_id =162 then 'Debit'
    when sale_id =163 then 'Debit'
    when sale_id = 165 then 'Cash'
    when sale_id =167 then 'Cash'
    when sale_id =169 then 'Debit'
    when sale_id =170 then 'Debit'
    when sale_id =171 then 'Debit'
    when sale_id =172 then 'Debit'
    when sale_id =174 then 'Debit'
    when sale_id =177 then 'Debit'
    when sale_id =179 then 'Cash'
    when sale_id =186 then 'Debit'
    when sale_id =187 then 'Debit'
    when sale_id =190 then 'Debit'
    when sale_id =198 then 'Debit'
    when sale_id =200 then 'Cash'
end
where sale_id in (3,7,9,12,20,22,26,27,32,34,36,41,45,50,53,58,59,61,68,70,75,77,80,81,83,88,94,97,99,107,108,113,114,116,110,118,119,121,123,129,131,132,135,135,139,141,142,144,146,147,148,151,154,155,161,162,163,165,167,169,170,171,172,174,177,179,186,187,190,198,200);


ALTER TABLE swiggy
ADD order_date_cleann DATE;

UPDATE swiggy
SET order_date_cleann =
CASE
    WHEN order_date LIKE '%-%' THEN STR_TO_DATE(order_date,'%m-%d-%Y')

    WHEN order_date LIKE '%/%' THEN STR_TO_DATE(order_date,'%m/%d/%Y')

    ELSE NULL
END;

SELECT order_date, order_date_cleann
FROM swiggy;

select * from swiggy;
alter table swiggy
drop column MyUnknownColumn;

ALTER TABLE swiggy
MODIFY Order_date_cleann VARCHAR(100) AFTER sale_id;

Alter table swiggy
rename column Order_date_cleann to Ordered;

update swiggy
set delivery_status='Delivery'
where sale_id =74;


UPDATE swiggy
SET City = TRIM(City);

UPDATE swiggy
SET City = LOWER(City);

UPDATE swiggy
SET City = 'Hyderabad'
WHERE City LIKE 'hyd%';

UPDATE swiggy
SET City = 'Chennai'
WHERE City LIKE 'chen%';

UPDATE swiggy
SET Pincode = TRIM(Pincode);

UPDATE swiggy
SET Pincode = '500000'
WHERE Pincode IS NULL OR Pincode='';

SELECT DISTINCT City, Pincode
FROM swiggy;
