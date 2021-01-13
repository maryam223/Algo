//PSEUDO-CODE


ALGO is_even
	data: ARRAY<NUMBER>
	dataSize: NUMBER
	i: NUMBER

START
	data <- [65, 2, 87, 30, 16, 5, 14, 67, 56, 8]
	dataSize <- data.LENGTH

	FOR i FROM 0 TO dataSize [ i <- i + 1 ]
		IF data[i] % 2 == 0
			PRINT (data[i] + " = pair ")
		ELSE 
			PRINT (data[i] + " != pair ")
		END IF
	END FOR
END ALGO

//Complexité

- data <- [65, 2, 87, 30, 16, 5, 14, 67, 56, 8] = 1
- dataSize <- data.LENGTH = 1
Total = 2

- i FROM 0 = 1
- 0 TO dataSize = 1
- i <- i + 1 = 1
- i + 1 = 1
- Test IF = 1

T(n) = 5n + 2


ALGO average
	data: ARRAY<NUMBER>
	dataSize: NUMBER
	i: NUMBER
	sum: NUMBER
	avg: NUMBER
	min: NUMBER
	max: NUMBER

START
	data <-  [65, 2, 87, 30, 16, 5, 14, 67, 56, 8]
	dataSize <- data.LENGTH
	sum <- 0
	min <- data[0]
	max <- data[0]

//Calcul Moyenne
	FOR i FROM 0 TO dataSize [ i <- i + 1 ]
		sum = sum + data[i]
	END FOR
	avg <- sum / dataSize
	
//Plus petit et plus grand du tableau
	FOR i FROM 0 TO dataSize [ i <- i + 1 ]
		IF min > data[i]
			min <- data[i]
		END IF
		IF max < data[i]
			max <- data[i]
		END IF
	END FOR

	PRINT ("Moyenne " + avg + " - Plus petit = " + min + ", Plus grand = " + max)

END

//Complexité

- data <-  [65, 2, 87, 30, 16, 5, 14, 67, 56, 8] = 1
- dataSize <- data.LENGTH = 1
- sum <- 0 = 1
- min <- data[0] = 1
- max <- data[0] = 1
Total = 5

- i FROM 0 = 1
- 0 TO dataSize = 1
- i <- i + 1 = 1
- i + 1 = 1
- Test IF = 1
- affectation dans max = 1

T(n) = 6n + 5




ALGO add_numbers_of_a_number
	number: INTEGER
	sum: INTEGER
	done: BOOLEAN
	to_add: INTEGER
	output: STRING

START
	number <- 123456789
	sum <- 0
	done <- False
	output <- ""

	WHILE done == false
		IF number == 0
			output <- output + "= " + sum
			done <- true
			PRINT (output)
		ELSE
			to_add <- number % 10
			sum <- sum + to_add
				IF number > 10
					output <- " + " + to_add + " " + output
				ELSE
					output <- to_add + " " + output
				END IF
			number <- number - to_add
			number <- number / 10
		END IF
	END WHILE

END

//Complexité

- number <- 123456789 = 1
- sum <- 0 = 1
- done <- False = 1
- output <- "" = 1

(Meilleur des cas)
- boucle while test done == false = 1
- test IF = 1
- output <- output + "= " + sum = 1
- done <- true = 1

T(n) = 4n + 4 (Meilleur des cas)

(Pire des cas)
- boucle while test done == false = 1
- test IF = 1
- to_add <- number % 10 = 1
- sum <- sum + to_add = 1
- test IF = 1
- affectation à output = 1
- number <- number - to_add = 1
- number <- number / 10 = 1
- output <- output + "= " + sum = 1
- done <- true = 1

T(n) = 10n + 4


//JAVASCRIPT

let data = [65, 2, 87, 30, 16, 5, 14, 67, 56, 8],
	dataSize = data.length;

for (var i = 0; i < dataSize; i++) {
	if (data[i]%2 == 0) {
		console.log(data[i] + " = pair");
	}else{
		console.log(data[i] + " != pair ");
	}
}

//

let sum = 0,
	min = data[0];
	max = data[0];
let avg;

for (var i = 0; i < dataSize; i++) {
	sum = sum + data[i];
}

avg = sum / dataSize;

for (var i = 0; i < dataSize ; i++) {
	if (min > data[i]) {
		min = data[i];
	}

	if (max<data[i]) {
		max = data[i];
	}
}

console.log("Moyenne " + avg + " - Plus petit = " + min + ", Plus grand = " + max);


//
let number = 123456789,
	done = false,
	output = "";
sum = 0;
let to_add;

while (done == false){
	if (number == 0) {
		output = output + "= " + sum;
			done = true
			console.log(output);
	}else{
		to_add = number%10;
		sum = sum + to_add;
		if(number > 10 ){
			output = "+ " + to_add + " " + output;
		}else{
			output = to_add + " " + output;
		}
		
		number = number - to_add;
		number = number / 10;
	}
}
