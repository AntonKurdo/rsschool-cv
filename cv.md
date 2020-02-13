# Anton Kurdo

#### Junior-Front-end developer/ trainee
----


#### Contacts:

- #####  tel: +375 33 614-33-28

- #####  e-mail: anton.kurdo@gmail.com

- ##### [LinkedIn](https://www.linkedin.com/in/anton-kurdo-4b22a311a/)

---

**Summary:** Current main goal is getting a job as Front-end developer. Also I'm looking for position of trainee to get a job exprerience in programming. Now I'm hardly learning JS, in the neares future I'm going to study React. I have already done 3 studying project in HTML/CSS, some of them You can find at [my github profile](https://github.com/AntonKurdo).

---

**Skills:** HTML5, CSS3, JavaScript, Bootstrap, jQuery, Gulp, Git


---

**Experience** I have no work experience as developer. Lately I worked as IT-recruiter. 

---


**Education** Now I'm attending a Front-end developer course at TeachMeSkills. The course program can be found [here](https://teachmeskills.by/kursy-programmirovaniya/frontend-html-css-javascript-minsk). Also I've done interactive courses at Html-Academy ([link to my profile here](https://htmlacademy.ru/profile/id1166619)).

Non-programming education: Master degree in History(BSU, Historical faculty). 

---

***English — B2 — Pre-Intermediate***

___


**Code example:**

```JavaScript
let photoInputEl = findInputEl();

let photosContainerEl = photosContainer();

var imagesUrls = [];

bindEnterClick(photoInputEl, photosContainerEl, imagesUrls);
restorePhotos(photosContainerEl, imagesUrls);```

```JavaScript
function findInputEl() {
   return document.querySelector('.js-new-photo')
};```

```JavaScript
function photosContainer() {
    return document.querySelector('.js-photos')
}```

```JavaScript
function bindEnterClick(photoInputEl, photosContainerEl, imagesUrls) {
    photoInputEl.addEventListener('keyup', (e) => {
        if (e.code == 'Enter') {
            //get url
            var src = photoInputEl.value;
            //create img with this url as img
            //create li with this img inside
            var li = document.createElement('li');
            li.innerHTML = `<img src = '${src}' />`
            //append this li to ul
            photosContainerEl.append(li);
            //push url to array
            imagesUrls.push(src);
            //save to localStorage
            localStorage.setItem('gallery', JSON.stringify(imagesUrls))
        }
    })
}```

```JavaScript
function restorePhotos(photosContainerEl, imagesUrls) {
    let photosStr = localStorage.getItem('gallery');
    if (!!photosStr) {
        let photos = JSON.parse(photosStr);
        photos.forEach((src) => {
            imagesUrls.push(src);
            //get url
            // var src = photoInputEl.value;
            //create img with this url as img
            //create li with this img inside
            var li = document.createElement('li');
            li.innerHTML = `<img src = '${src}' />`;
            //append this li to ul
            photosContainerEl.append(li);
        });
    }
}```