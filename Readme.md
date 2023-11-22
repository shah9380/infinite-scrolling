# Infinite Scrolling Gallery

![image](https://github.com/shah9380/infinite-scrolling/assets/130676464/fa60ce5b-89a7-4799-b43e-8e14b573a984)


## Description

This project is an infinite scrolling gallery that fetches images from the Pixabay API. It provides a visually appealing way to explore images with a rubber effect on hover.

## Live Demo

Explore the gallery: [Infinite Scrolling Gallery](https://shah9380.github.io/infinite-scrolling/)

## Screenshots

Include screenshots or GIFs to showcase the application.

## Features

- **Infinite Scrolling:** Load more images dynamically as you scroll to the bottom of the page.
- **Rubber Effect on Hover:** Cards and images scale and rotate for a playful interaction.

## Technologies Used

- HTML
- CSS
- JavaScript

## Infinite Scrolling Implementation

Infinite scrolling is achieved using the following steps:

1. **Fetch API:** Images are fetched from the Pixabay API using JavaScript's `fetch` function.

    ```javascript
    const response = await fetch(`https://pixabay.com/api/?key=${apikey}&page=${page}`);
    const data = await response.json();
    ```

2. **Render Data:** The fetched data is rendered on the page using JavaScript. Each image is wrapped in an anchor (`<a>`) element, linking to its original page on Pixabay.

    ```javascript
    function renderData(details) {
        details.forEach((element) => {
            const imageContainer = document.createElement('a');
            imageContainer.classList.add('image-container');
            imageContainer.href = element.pageURL;
            imageContainer.target = '_blank';

            const image = document.createElement('img');
            image.src = element.webformatURL;
            image.alt = element.tags;

            imageContainer.appendChild(image);
            containerImage.appendChild(imageContainer);
        });
    }
    ```

3. **Infinite Scroll Event Listener:** An event listener is added to the `scroll` event of the window. When the user reaches the bottom of the page, the `DataSet` function is called with an incremented page number.

    ```javascript
    window.addEventListener('scroll', () => {
        if (window.innerHeight + window.scrollY >= document.body.offsetHeight) {
            // When the user reaches the bottom of the page, load more data
            DataSet(page);
            page++;
        }
    });
    ```

## How to Use

1. Visit the live demo link: [Infinite Scrolling Gallery](https://shah9380.github.io/infinite-scrolling/).
2. Scroll down to load more images dynamically.
3. Hover over images to experience the rubber effect.

## Installation

If you want to run the project locally, follow these steps:

1. Clone the repository:

    ```bash
    git clone https://github.com/shah9380/infinite-scrolling.git
    ```

2. Open the `index.html` file in your web browser.

## Contributing

Contributions are welcome!.


## Acknowledgments

- Images are fetched from the [Pixabay API](https://pixabay.com/).
- Special thanks to [OpenAI](https://www.openai.com/) for language model support.

## Contact

For any inquiries or feedback, please contact the project maintainer:

[Shah Misbahul Islam]
[shahislam9380@gmail.com]

---
