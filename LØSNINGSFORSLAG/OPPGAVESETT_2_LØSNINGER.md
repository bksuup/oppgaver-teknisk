# Løsningsforslag

## Oppgaver med GREP

1. Hvor mange oppføringer har timestamp i 2021? \
	210 \
		```grep ",2021" sample_data.csv -c```

2. Hvor mange navn starter på bokstaven B? \
	56 \
		```grep ",B" sample_data.csv -c```

3. Hvor mange navn har bokstaven f i seg? \
	60 \
		```grep -i "f" sample_data.csv -c```


## Oppgaver med AWK

1. Print ut bare navn og epost addresse for alle brukere \
	```awk -F "," '{print $2, $3}' sample_data.csv```

2. Print ut kolonne 1 og 2 med en blankspace " " som delimiter \
	```awk -F " " '{print $1, $2}' sample_data.csv```


## Oppgaver med GREP og AWK

1. Print ID for oppføringene som har ip-addresse 127.0.0.123 \
	```grep "127.0.0.123" sample_data.csv | awk -F "," '{print $1}'```
	
2. Print Navn, epost og Timestand for oppføringen som har eposten "@example.com" \
	```grep "@example.com" sample_data.csv | awk -F "," '{print $2, $3, $5}'```

3. Print id og ip for alle oppføringer med ipaddressen 127.0.0.1 \
	```grep "127.0.0.1," sample_data.csv | awk -F "," '{print $1, $4}'```
