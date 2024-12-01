airbnb
  | (frontend react app)
  |_client > src > pages_IndexPage
  |                     |_LoginPage
  |                     |_RegisterPage
  |     
  |                      
  |  (express backend app) 
  |__api > models > User.js
        |_ index.js


INSTALLATION GUIDE:
before creating folders,
`npm install --gobal yarn` 
`yarn init (type project names)`
`yarn install`
"stop reactjs app before adding packages with yarn"

creating folders,
yarn create vite client > React > JavaScript
-once client directory up, from terminal, cd client folder > yarn;
-after yarn installed in client> directory, type `yarn dev`; (to get port number for browser open)
-add React Dev Tools Chrome extension on Chrome browser

airbnb-clone\api>`npm install express` 
airbnb-clone\api>`yarn install cors`
airbnb-clone\api>`yarn add mongoose`
airbnb-clone\api>`yarn add dotenv`
airbnb-clone\api>`yarn add bcryptjs`
airbnb-clone\api>`yarn add jsonwebtoken`
1:39 airbnb-clone\api>`yarn add cookie-parser`
2:55 airbnb-clone\api>`yarn add image-downloader`
3:12 airbnb-clone\api>`yarn add multer`
5:53 airbnb-clone\client>`yarn add date-fns`
PARTS:
1:29 show login user on index page
2:10 my places setup
2:40 add useState for form
2:44 create function for <div>
2:48 create function for Perks
2:49 create input IDs for testarea fields{title}{address}                                       
2:54 create add photo function
3:06-3:15 create upload function skip to 3:17
3:28 create checkbox function
3:34 refactor Photos add, upload into PhotoUploader.jsx
3:39 form submit 
3:54 - 4:04 refactoring
4:05 list added-places at "My places" > PlacesPage.jsx
      app.get('/user-places')
4:22 updating places 
4:34 delete photos > PhotoUpLoader.jsx
4:39 main cover photo > PhotoUpLoader.jsx
4:45 index page setup
5:03 link to index 'public' page photos > PlacePage.jsx
      app.get('/places/:id')
5:31 place bookings > PlacePage.jsx 
5:41 bookings boxes > PlacePage.jsx
5:50 booking page > name, emal fields
6:00 booking data endpoint
6:03 booking schema > Bookings.js
6:24 link booking.id
6:30 creating place.photos as a separate component
6:40 creating booked places info page
6:47 create PlaceGallery > PlaceGallery.jsx
6:49 create component for AddressLink.jsx
6:53 create component for bookingDates

______________________________________________________
start up app
cd client > `yarn dev`;
http://localhost:5173
cd api > `nodemon start`;
process.env.PORT || 3000
______________________________________________________

DEPLOYMENT - DOCKER
Docker Tutorial for Beginners(3hrs)
30:15 docker Win 10 installation
1:13 Mongo express (container = mongo UI)

DOCKER - PROGRESS 
video stopped at 31:33 docker config
linux setup stopped at 42:00 docker config
Basic commands 42:03

Follow steps to containerize Node.js app here
https://docs.docker.com/language/nodejs/containerize/

TERMINAL STEPS
"initialize docker" $docker init
"created" Dockerfile, .dockerignore, compose.yaml
"run app" $docker compose up --build
"run app as detached mode" $docker compose up --build -d
"stop app" $docker compose down

MONGO DB 
user: mckeenweb
collections: test [bookings, places, users]

