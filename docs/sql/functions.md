---
layout: default
title: Functions
parent: SQL
nav_order: 10
---

# Functions

You must enable fielddata in the document mapping for most string functions to work properly.

The specification shows the return type of the function with a generic type `T` as the argument.
For example, `abs(number T) -> T` means that the function `abs` accepts a numerical argument of type `T`, which could be any sub-type of the `number` type, and it returns the actual type of `T` as the return type.

Function | Specification | Example
:--- | :--- | :---
abs | `abs(number T) -> T` | `SELECT abs(0.5) FROM my-index LIMIT 1`
acos | `acos(number T) -> double` | `SELECT acos(0.5) FROM my-index LIMIT 1`
add | `add(number T, number) -> T` | `SELECT add(1, 5) FROM my-index LIMIT 1`
ascii | `ascii(string T) -> integer` | `SELECT ascii(name.keyword) FROM my-index LIMIT 1`
asin | `asin(number T) -> double` | `SELECT asin(0.5) FROM my-index LIMIT 1`
atan | `atan(number T) -> double` | `SELECT atan(0.5) FROM my-index LIMIT 1`
atan2 | `atan2(number T, number) -> double` | `SELECT atan2(1, 0.5) FROM my-index LIMIT 1`
cbrt | `cbrt(number T) -> T` | `SELECT cbrt(0.5) FROM my-index LIMIT 1`
ceil | `ceil(number T) -> T` | `SELECT ceil(0.5) FROM my-index LIMIT 1`
concat_ws | `concat_ws(separator, string, string…) -> string` | `SELECT concat_ws("-", "Tutorial", "is", "fun!") FROM my-index LIMIT 1`
cos | `cos(number T) -> double` | `SELECT cos(0.5) FROM my-index LIMIT 1`
cosh | `cosh(number T) -> double` | `SELECT cosh(0.5) FROM my-index LIMIT 1`
cot | `cot(number T) -> double` | `SELECT cot(0.5) FROM my-index LIMIT 1`
curdate | `curdate() -> date` | `SELECT curdate() FROM my-index LIMIT 1`
date | `date(date) -> date` | `SELECT date() FROM my-index LIMIT 1`
date_format | `date_format(date, string) -> string` or `date_format(date, string, string) -> string` | `SELECT date_format(date, 'Y') FROM my-index LIMIT 1`
dayofmonth | `dayofmonth(date) -> integer` | `SELECT dayofmonth(date) FROM my-index LIMIT 1`
degrees | `degrees(number T) -> double` | `SELECT degrees(0.5) FROM my-index LIMIT 1`
divide | `divide(number T, number) -> T` | `SELECT divide(1, 0.5) FROM my-index LIMIT 1`
e | `e() -> double` | `SELECT e() FROM my-index LIMIT 1`
exp | `exp(number T) -> T` | `SELECT exp(0.5) FROM my-index LIMIT 1`
expm1 | `expm1(number T) -> T` | `SELECT expm1(0.5) FROM my-index LIMIT 1`
floor | `floor(number T) -> T` | `SELECT floor(0.5) AS Rounded_Down FROM my-index LIMIT 1`
if | `if(boolean, es_type, es_type) -> es_type` | `SELECT if(false, 0, 1) FROM my-index LIMIT 1`, `SELECT if(true, 0, 1) FROM my-index LIMIT 1`
ifnull | `ifnull(es_type, es_type) -> es_type` | `SELECT ifnull('hello', 1) FROM my-index LIMIT 1`, `SELECT ifnull(null, 1) FROM my-index LIMIT 1`
isnull | `isnull(es_type) -> integer` | `SELECT isnull(null) FROM my-index LIMIT 1`, `SELECT isnull(1) FROM my-index LIMIT 1`
left | `left(string T, integer) -> T` | `SELECT left('hello', 2) FROM my-index LIMIT 1`
length | `length(string) -> integer` | `SELECT length('hello') FROM my-index LIMIT 1`
ln | `ln(number T) -> double` | `SELECT ln(10) FROM my-index LIMIT 1`
locate | `locate(string, string, integer) -> integer` or `locate(string, string) -> INTEGER` | `SELECT locate('o', 'hello') FROM my-index LIMIT 1`, `SELECT locate('l', 'hello', 3) FROM my-index LIMIT 1`
log | `log(number T) -> double` or `log(number T, number) -> double` | `SELECT log(10) FROM my-index LIMIT 1`
log2 | `log2(number T) -> double` | `SELECT log2(10) FROM my-index LIMIT 1`
log10 | `log10(number T) -> double` | `SELECT log10(10) FROM my-index LIMIT 1`
lower | `lower(string T) -> T` or `lower(string T, string) -> T` | `SELECT lower(name.keyword) FROM my-index LIMIT 1`
ltrim | `ltrim(string T) -> T` | `SELECT ltrim(name.keyword) FROM my-index`
maketime | `maketime(integer, integer, integer) -> date` | `SELECT maketime(1, 2, 3) FROM my-index LIMIT 1`
modulus | `modulus(number T, number) -> T` | `SELECT modulus(2, 3) FROM my-index LIMIT 1`
month | `month(date) -> integer` | `SELECT month(date) FROM my-index`
monthname | `monthname(date) -> string` | `SELECT monthname(date) FROM my-index`
multiply | `multiply(number T, number) -> number` | `SELECT multiply(2, 3) FROM my-index LIMIT 1`
now | `now() -> date` | `SELECT now() FROM my-index LIMIT 1`
pi | `pi() -> double` | `SELECT pi() FROM my-index LIMIT 1`
pow | `pow(number T) -> T` or `pow(number T, number) -> T` | `SELECT pow(2, 3) FROM my-index LIMIT 1`
power | `power(number T) -> T` or `power(number T, number) -> T` | `SELECT power(2, 3) FROM my-index LIMIT 1`
radians | `radians(number T) -> double` | `SELECT radians(0.5) FROM my-index LIMIT 1`
rand | `rand() -> number` or `rand(number T) -> T` | `SELECT rand(0.5) FROM my-index LIMIT 1`
replace | `replace(string T, string, string) -> T` | `SELECT replace('hello', 'l', 'x') FROM my-index LIMIT 1`
right | `right(string T, integer) -> T` | `SELECT right('hello', 1) FROM my-index LIMIT 1`
rint | `rint(number T) -> T` | `SELECT rint(1.5) FROM my-index LIMIT 1`
round | `round(number T) -> T` | `SELECT round(1.5) FROM my-index LIMIT 1`
rtrim | `rtrim(string T) -> T` | `SELECT rtrim(name.keyword) FROM my-index LIMIT 1`
sign | `sign(number T) -> T` | `SELECT sign(1.5) FROM my-index LIMIT 1`
signum | `signum(number T) -> T` | `SELECT signum(0.5) FROM my-index LIMIT 1`
sin | `sin(number T) -> double` | `SELECT sin(0.5) FROM my-index LIMIT 1`
sinh | `sinh(number T) -> double` | `SELECT sinh(0.5) FROM my-index LIMIT 1`
sqrt | `sqrt(number T) -> T` | `SELECT sqrt(0.5) FROM my-index LIMIT 1`
substring | `substring(string T, integer, integer) -> T` | `SELECT substring(name.keyword, 2,5) FROM my-index LIMIT 1`
subtract | `subtract(number T, number) -> T` | `SELECT subtract(3, 2) FROM my-index LIMIT 1`
tan | `tan(number T) -> double` | `SELECT tan(0.5) FROM my-index LIMIT 1`
timestamp | `timestamp(date) -> date` | `SELECT timestamp(date) FROM my-index LIMIT 1`
trim | `trim(string T) -> T` | `SELECT trim(name.keyword) FROM my-index LIMIT 1`
upper | `upper(string T) -> T` or `upper(string T, string) -> T` | `SELECT upper(name.keyword) FROM my-index LIMIT 1`
year | `year(date) -> integer` | `SELECT year(date) FROM my-index LIMIT 1`
/ | `number [op] number -> number` | `SELECT 1 / 100 FROM my-index LIMIT 1`
% | `number [op] number -> number` | `SELECT 1 % 100 FROM my-index LIMIT 1`
