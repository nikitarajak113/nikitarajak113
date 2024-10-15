<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Image Gallery</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .gallery-container {
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
            overflow: hidden;
            text-align: center;
        }
        .image-display {
            margin: 20px 0;
        }
        img {
            max-width: 100%;
            height: auto;
        }
        .thumbnail-container {
            display: flex;
            justify-content: center;
            margin: 20px 0;
        }
        .thumbnail {
            width: 100px;
            height: auto;
            margin: 0 5px;
            cursor: pointer;
            opacity: 0.6;
            transition: opacity 0.3s;
        }
        .thumbnail:hover {
            opacity: 1;
        }
        .navigation {
            margin: 20px 0;
        }
        button {
            padding: 10px 15px;
            margin: 0 10px;
            border: none;
            border-radius: 5px;
            background-color: #007bff;
            color: white;
            cursor: pointer;
        }
        button:hover {
            background-color: #0056b3;
        }
    </style>
</head>
<body>
    <div class="gallery-container">
        <div class="image-display">
            <img id="currentImage" src="image1.jpg" alt="Gallery Image">
        </div>
        <div class="navigation">
            <button id="prevButton">Previous</button>
            <button id="nextButton">Next</button>
        </div>
        <div class="thumbnail-container">
            <img class="thumbnail" src="image1.jpg" alt="Thumbnail 1" onclick="changeImage(0)">
            <img class="thumbnail" src="image2.jpg" alt="Thumbnail 2" onclick="changeImage(1)">
            <img class="thumbnail" src="image3.jpg" alt="Thumbnail 3" onclick="changeImage(2)">
            <img class="thumbnail" src="image4.jpg" alt="Thumbnail 4" onclick="changeImage(3)">
            <img class="thumbnail" src="image5.jpg" alt="Thumbnail 5" onclick="changeImage(4)">
        </div>
    </div>

    <script>
        const images = [
            'image1.jpg',
            'image2.jpg',
            'image3.jpg',
            'image4.jpg',
            'image5.jpg'
        ];

        let currentIndex = 0;

        const currentImage = document.getElementById('currentImage');

        document.getElementById('prevButton').addEventListener('click', () => {
            currentIndex = (currentIndex > 0) ? currentIndex - 1 : images.length - 1;
            updateImage();
        });

        document.getElementById('nextButton').addEventListener('click', () => {
            currentIndex = (currentIndex < images.length - 1) ? currentIndex + 1 : 0;
            updateImage();
        });

        function changeImage(index) {
            currentIndex = index;
            updateImage();
        }

        function updateImage() {
            currentImage.src = images[currentIndex];
        }
    </script>
</body>
</html> 
 
