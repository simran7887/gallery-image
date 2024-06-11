body {
    font-family: Arial, sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
    background-color: #f0f0f0;
}

.gallery-container {
    position: relative;
    width: 80%;
    max-width: 800px;
    margin: auto;
    overflow: hidden;
}

.gallery {
    display: flex;
    transition: transform 0.5s ease-in-out;
}

.gallery img {
    width: 100%;
    flex-shrink: 0;
}

.controls {
    display: flex;
    justify-content: space-between;
    margin-top: 10px;
}

.controls button {
    padding: 10px 20px;
    background-color: #007BFF;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

.controls button:hover {
    background-color: #0056b3;
}

.gallery img {
    max-width: 100%;
    /* height: auto; Maintain aspect ratio */
}
 42 changes: 42 additions & 0 deletions42  
IMAGE GALLERY/codeAlphaTask1.html
Original file line number	Diff line number	Diff line change
@@ -0,0 +1,42 @@
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Image Gallery</title>
    <link rel="stylesheet" href="codeAlphaTask1.css">
</head>
<body>
    <div class="gallery-container">
        <div class="gallery">
            <img src="https://www.abhibus.com/blog/wp-content/uploads/2023/12/Hidimba-Devi-Temple.jpg" alt="Image 1" width="600" height="600">
            <img src="https://img.freepik.com/free-photo/fresh-yellow-daisy-single-flower-close-up-beauty-generated-by-ai_188544-15543.jpg?size=626&ext=jpg&ga=GA1.1.1224184972.1714521600&semt=ais" alt="Image 3" width="600" height="600">
            <img src="https://lp-cms-production.imgix.net/2019-06/GettyImages-149353949_high.jpg" alt="Image 2" width="600" height="600">

            <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/cb/Howrah_bridge_at_night.jpg/1200px-Howrah_bridge_at_night.jpg" alt="Image 1" width="600" height="600">
            <img src="https://i.natgeofe.com/k/e2ffc795-8b1f-4479-8c95-b6497e5ca4f2/canada-vancouver_4x3.jpg?wp=1&w=1084.125&h=813.75" alt="Image 3" width="600" height="600">
            <img src="https://i.pinimg.com/originals/ae/59/45/ae59451ac6139db849c9609325cbde83.jpg" alt="Image 2" width="600" height="600">

            <img src="https://cricketaddictor.com/wp-content/uploads/2023/09/India-National-Cricket-Team.jpg" alt="Image 1" width="600" height="600">
            <img src="https://okcredit-blog-images-prod.storage.googleapis.com/2020/09/Entrepreneurship.jpg" alt="Image 3" width="600" height="600">
            <img src="https://www.themanual.com/wp-content/uploads/sites/9/2021/02/formula-one-abu-dhabi-2020.jpg?p=1" alt="Image 2" width="600" height="600">

            <img src="https://media.radissonhotels.net/image/marketing-campaigns-cese/promotional/16256-147379-f74701594_3xl.jpg?impolicy=HomeHero" alt="Image 1" width="600" height="600">
            <img src="https://media.istockphoto.com/id/471921497/photo/people-of-himachal-pradesh-senior-man-using-laptop-with-family.jpg?s=612x612&w=0&k=20&c=NDs-fxXiR5iHw9_vaMVZBswlf-ni5uj4azmmQNFcHac=" alt="Image 3" width="600" height="600">
            <img src="https://dynamic-media-cdn.tripadvisor.com/media/photo-o/1c/63/39/1b/northern-lights-village.jpg?w=1200&h=-1&s=1" alt="Image 2" width="600" height="600">

            <img src="https://i.natgeofe.com/k/88de42b8-764c-40d2-89ee-e72d55dc95b8/emperor-penguin-chicks.jpg" alt="Image 1" width="600" height="600">
            <img src="https://media1.thrillophilia.com/filestore/tzr4oea03sp7rlt8wkj8n9z5umeg_shutterstock_761034820.jpg" alt="Image 3" width="600" height="600">
            <img src="https://images.pexels.com/photos/771883/pexels-photo-771883.jpeg?cs=srgb&dl=pexels-rbrigant44-771883.jpg&fm=jpg" alt="Image 2" width="600" height="600">
            <!-- Add more images as needed -->
        </div>

        <div class="controls">
            <button id="prev">Previous</button>
            <button id="next">Next</button>
        </div>
    </div>

    <script src="codeAlphaTask1.js"></script>
</body>
</html>
 32 changes: 32 additions & 0 deletions32  
IMAGE GALLERY/codeAlphaTask1.js
Original file line number	Diff line number	Diff line change
@@ -0,0 +1,32 @@
document.addEventListener("DOMContentLoaded", () => {
    const gallery = document.querySelector('.gallery');
    const images = document.querySelectorAll('.gallery img');
    const prevButton = document.getElementById('prev');
    const nextButton = document.getElementById('next');

    let currentIndex = 0;

    function showImage(index) {
        if (index < 0) {
            currentIndex = images.length - 1; // Loop to the last image
        } else if (index >= images.length) {
            currentIndex = 0; // Loop to the first image
        }
        const offset = -currentIndex * 100;
        gallery.style.transform = `translateX(${offset}%)`;
        console.log(`Showing image ${currentIndex + 1} of ${images.length}`);
    }

    prevButton.addEventListener('click', () => {
        currentIndex--;
        showImage(currentIndex);
    });

    nextButton.addEventListener('click', () => {
        currentIndex++;
        showImage(currentIndex);
    });

    // Show the first image initially
    showImage(currentIndex);
});
 
