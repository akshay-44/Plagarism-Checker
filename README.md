# Plagarism-Checker
Plagarism Checker From Open HTML, CSS & JS

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Plagiarism Checker</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f4f4f4;
        }

        #plagiarism-checker {
            max-width: 600px;
            width: 100%;
            padding: 20px;
            background-color: white;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            border-radius: 8px;
        }

        textarea {
            width: 100%;
            height: 100px;
            margin-bottom: 10px;
            padding: 10px;
            box-sizing: border-box;
        }

        button {
            background-color: #4caf50;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
    </style>
</head>
<body>

<div id="plagiarism-checker">
    <h2>Plagiarism Checker</h2>
    <textarea id="inputText1" placeholder="Enter text 1..."></textarea>
    <textarea id="inputText2" placeholder="Enter text 2..."></textarea>
    <button onclick="checkPlagiarism()">Check Plagiarism</button>
    <p id="plagiarismResult"></p>
</div>

<script>
    function checkPlagiarism() {
        var text1 = document.getElementById("inputText1").value;
        var text2 = document.getElementById("inputText2").value;

        var similarityPercentage = calculateSimilarity(text1, text2);

        document.getElementById("plagiarismResult").innerText = "Similarity: " + similarityPercentage.toFixed(2) + "%";
    }

    function calculateSimilarity(text1, text2) {
        // This is a placeholder function for a basic similarity calculation
        // You may need more advanced algorithms for accurate results
        var commonWords = text1.split(' ').filter(word => text2.split(' ').includes(word));

        var similarityPercentage = (commonWords.length / Math.max(text1.split(' ').length, text2.split(' ').length)) * 100;

        return similarityPercentage;
    }
</script>

</body>
</html>
