<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Roulette</title>
  <style>
    #roulette-container {
      width: 100%;
      height: 130px;
      border: 4px solid black;
      position: relative;
      overflow: hidden;
    }
    #roulette-images {
      position: absolute;
      top: 0;
      left: 0;
      display: flex;
      transition: transform 10s cubic-bezier(0.00001, 0.003, 0.001, 1);
    }
    .roulette-image-container {
      width: 100px;
      height: 130px;
      border-right: 2px solid black; /* Ajout de la bordure à droite */
      box-sizing: border-box; /* Assure que la bordure fait partie de la largeur de l'image */
    }
    .roulette-image {
      width: 100%;
      height: 100%;
    }
    #stop-line {
      position: absolute;
      top: 0;
      left: calc(50% - 1.5px + 16px);
      width: 3px;
      height: 100%;
      background-color: red;
    }
  </style>
</head>
<body>
  <div id="roulette-container">
    <div id="roulette-images"></div>
    <div id="stop-line"></div>
  </div>
  <button id="start-button">Start</button>

  <script>
    const images = [
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      {url: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27', chance: 0.5, redirectUrl: 'https://brick2brick.shop/assets/images/image263.jpg?v=c5638f27' },
      

      

      // Ajouter d'autres images ici...
    ];

    const rouletteImagesElement = document.getElementById('roulette-images');
    const stopLineElement = document.getElementById('stop-line');
    const startButton = document.getElementById('start-button');

    function startAnimation() {
      rouletteImagesElement.style.transform = 'translateX(-3000px)';
    }

    function stopAnimation() {
      rouletteImagesElement.style.transform = 'none';
    }

    function getVisibleImage() {
      const stopLinePosition = stopLineElement.getBoundingClientRect().left + (stopLineElement.offsetWidth / 2);
      const images = document.querySelectorAll('.roulette-image');
      let visibleRedirectUrl = null;

      images.forEach(image => {
        const imagePosition = image.getBoundingClientRect().left + (image.offsetWidth / 2);
        if (imagePosition > stopLinePosition && visibleRedirectUrl === null) {
          visibleRedirectUrl = image.dataset.redirectUrl; // Accédez à l'URL de redirection à partir de l'attribut dataset
        }
      });

      return visibleRedirectUrl;
    }

    startButton.addEventListener('click', () => {
      startAnimation();
      startButton.disabled = true;

      setTimeout(() => {
        const result = getVisibleImage();
        window.location.href = result; // Rediriger vers l'URL de redirection
      }, 10000); // Réduire la durée de la transition ici
    });

    // Charger les images en tenant compte des chances et de manière aléatoire
    window.addEventListener('load', () => {
      images.forEach(image => {
        const numDuplicates = Math.round(image.chance * 100); // Nombre d'images à dupliquer
        for (let i = 0; i < numDuplicates; i++) {
          const container = document.createElement('div');
          container.classList.add('roulette-image-container');

          const img = document.createElement('img');
          img.src = image.url;
          img.classList.add('roulette-image');
          img.dataset.redirectUrl = image.redirectUrl; // Définissez l'URL de redirection dans l'attribut dataset
          container.appendChild(img);

          // Insérer l'image à un index aléatoire
          const randomIndex = Math.floor(Math.random() * rouletteImagesElement.children.length);
          rouletteImagesElement.insertBefore(container, rouletteImagesElement.children[randomIndex]);
        }
      });
    });
  </script>
</body>
</html>
