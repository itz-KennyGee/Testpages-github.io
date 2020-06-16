<!DOCTYPE html>
<html>

<head>
    <title> Convert </title>
    <style>
        body {
            display: flex;
            font-family: Helvetica;
        }

        @media only screen and (max-width: 858px) {
            body {
                flex-direction: column;
            }
        }

        .section {
            height: 100vh;
            width: 50%;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 20px;

        }

        @media only screen and (max-width: 858px) {
            .section {
                width: 100%;
            }
        }


        #section-1 {
            background-color: #f2f2f2;
        }

        #section-2 {
            background-color: #d9d9d9;
        }

        .content {
            max-width: 100%;
            width: 400px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }

        h2 {
            font-size: 1.5em;
            font-family: 'Helvetica';
            margin-bottom: 12px;
        }

        .result {
            font-size: 1em;
            font-weight: bold;
            position: absolute;
            bottom: 16%;

        }

        .section input {
            width: 100%;
            margin-top: 12px;
            margin-bottom: 12px;
            padding: 12px;
            font-family: Helvetica;
        }

        .section button {
            width: 35%;
            border: solid 2px #191919;
            color: white;
            background-color: #191919;
            padding: 10px;
            transition: ease-in-out 0.2s;
            cursor: pointer;
        }

        .section button:hover {
            background-color: transparent;
            border: solid 2px #191919;
            color: #191919;
        }
    </style>
</head>

<body>
    <section id="section-1" class="section">
        <div class="content">
            <h2>Integer to String Converter</h2>

            <script>

                function toString(num) {
                    var units = ['', 'one', 'two', 'three', 'four', 'five', 'six', 'seven', 'eight', 'nine'];
                    var tenplus = ['ten', 'eleven', 'twelve', 'thirteen', 'fourteen', 'fifteen', 'sixteen', 'seventeen', 'eighteen', 'nineteen'];
                    var tens = ['', '', 'twenty', 'thirty', 'forty', 'fifty', 'sixty', 'seventy', 'eighty', 'ninety'];
                    var power = ['', '', 'hundred', 'thousand'];

                    num = document.getElementById("num").value;
                    var readout = '';

                    number = num.toString();
                    // number = number.split("");
                    var length = number.length;

                    if (num == 0) {
                        readout = 'zero'
                    } else if (length == 1) {
                        readout = (units[number])
                    } else if (length == 2) {
                        if (number[0] == '1') {
                            readout = (tenplus[number[1]])
                        } else {
                            if (number[1] == '0') { readout = tens[number[0]] } else {
                                readout = tens[number[0]] + ' ' + units[number[1]]
                            }
                        }
                    } else if (length >= 3) {
                        var i = 0;
                        while (i < length - 2) {
                            if (number[i] > 0) {
                                readout = readout.concat(units[number[i]] + ' ' + power[length - (i + 1)] + ' ');
                            } else { readout = readout.concat(' ') }
                            i++;
                        }
                        if ((i = length - 2) && (number[i] > 0)) { //maybe while instead of if?
                            if (number[i] == 1) {
                                readout = readout.concat('and ' + tenplus[number[i + 1]])
                            } else if (number[i] > 1) {
                                readout = readout.concat('and ' + tens[number[i]] + ' ' + units[number[i + 1]])
                            }
                        } else if ((number[i] == 0) && number[i + 1] > 0) { readout = readout.concat('and ' + units[number[i + 1]]) }
                        else { readout = readout }
                    }

                    if (length > 4) { readout = "Sorry, numbers above 9999 not supported." }

                    return readout;
                }


                function myFunction() {

                    document.getElementById("demo-string").innerHTML = toString(num);
                }


            </script>

            <p> <label> Enter the number below: </label> <input type="number" id="num" value=""> </p>
            <button onclick="myFunction()">
                Convert </button>

            <p id="demo-string" class="result"> Result will display here. </p>
        </div>
    </section>

    <section id="section-2" class="section">
        <div class="content">
            <h2> String to Integer Converter</h2>

            <script>
                function toInteger(words) {
                    var units = ['', 'one', 'two', 'three', 'four', 'five', 'six', 'seven', 'eight', 'nine'];
                    var tenplus = ['ten', 'eleven', 'twelve', 'thirteen', 'fourteen', 'fifteen', 'sixteen', 'seventeen', 'eighteen', 'nineteen'];
                    var tens = ['', '', 'twenty', 'thirty', 'forty', 'fifty', 'sixty', 'seventy', 'eighty', 'ninety'];
                    var power = ['', '', 'hundred', 'thousand'];

                    words = document.getElementById("words").value;
                    words = words.toLowerCase();

                    words = words.split(' ');
                    if (words.indexOf('and') > -1) { words.splice(words.indexOf('and'), 1) }
                    var length = words.length;
                    var int = 0;


                    for (var i = length - 1; i >= 0; i--) {
                        if (units.indexOf(words[i]) > -1) {
                            int += units.indexOf(words[i]);
                        } else if (tenplus.indexOf(words[i]) > -1) {
                            int += 10 + tenplus.indexOf(words[i]);
                        } else if (tens.indexOf(words[i]) > -1) {
                            int += 10 * tens.indexOf(words[i]); // last 2 digits sorted 
                        } if (power.indexOf(words[i]) > 1) {
                            int += (10 ** power.indexOf(words[i])) * (units.indexOf(words[i - 1]));
                            i--
                        }

                    }
                    return int

                }

                function myFunction2() {
                    document.getElementById("demo-number").innerHTML = toInteger(words);
                }
            </script>

            <p> <label> Enter your text below:</label> <input type="text" id="words" value=""> </p>
            <button onclick="myFunction2()">
                Convert </button>

            <p id="demo-number" class="result"> Result will display here. </p>
        </div>
    </section>
</body>

</html>
