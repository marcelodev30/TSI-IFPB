


## Qual é o nome do governante do Reino Unido (United Kingdom) e o tipo de governo?
```mysql
select HeadOFState as "Governante",GovernmentForm as "Tipo de governo" from country  where Name="United Kingdom";
```


## Quais países possuem uma população superior a 200 milhões e falam a língua portuguesa?
```mysql
select Name from countrylanguage ,country where countrylanguage.CountryCode =country.Code and Population > 20000000 and countrylanguage.Language = "Portuguese";
```

## Quais países têm a língua inglesa como oficial e obtiveram independência antes de 1900?
```mysql
select name from countrylanguage,country  where countrylanguage.CountryCode = country.Code  and Language = "English" and isOfficial= "T" and IndepYear <= 1900;
```

## Quais países da América Latina têm uma população superior a 20 milhões e falam português?
```mysql
select Name from countrylanguage,country  where countrylanguage.CountryCode = country.Code  and  (Region ="South America" or Region ="Central America") and Language = "Portuguese" and Population > 2000000;
```

## Quais são os países onde o governante é "Nelson Mandela" e a língua oficial é "Afrikaans"?
```mysql
select * from countrylanguage,country  where countrylanguage.CountryCode = country.Code  and Language= "Afrikaans" and IsOfficial = "T"  and  HeadOFState = "Nelson Mandela" ;
```

## Exibir os países da Europa com sua população, onde a língua oficial é o alemão e o governo é uma monarquia.
```mysql
select Name from countrylanguage,country  where countrylanguage.CountryCode = country.Code and Continent = 'Europe' and Language='German' and IsOfficial= 'T' and GovernmentForm = 'Constitutional Monarchy';
```

## Quais são os países independentes desde o século XIX e falam francês?
```mysql
select Name from countrylanguage,country where countrylanguage.CountryCode = country.Code and (IndepYear >= 1800 and IndepYear <=1900) and Language = 'French';
```

## Quais países da América do Sul têm uma população maior que 20 milhões e o tipo de governo é uma república?
```mysql
select GovernmentForm from country where Region= 'South America' and Population > 20000000 ;
```

## Qual é a média da população dos países que falam espanhol e possuem mais de 10 milhões de habitantes?
```mysql
select avg(Population) as 'Média da População' from countrylanguage,country  where countrylanguage.CountryCode = country.Code and Language="Spanish" and Population > 10000000;
```


## Qual é a população total de países na Ásia que falam chinês?
```mysql
select sum(Population) as 'População Total' from countrylanguage,country  where countrylanguage.CountryCode = country.Code and Language= 'Chinese' and Continent = 'Asia';
```
