<a name="readme-top"></a>

<!-- DMC Logo -->
<div align="center">
  <img src="https://user-images.githubusercontent.com/112587650/253305295-f548caac-b273-4f40-b29e-f5284e94109a.jpeg" alt="DMC Logo" width="50%" height="200">
</div>

<!-- Main Image -->
<div>
  <div style="display: flex; justify-content: space-between;">
  <img src="https://github.com/Drala-Mountain-Center-App/dmc_front_end/assets/115356592/fd463a24-485d-4b04-938f-94d1d1689d2e" alt="timer" width=30% />
  <img src="https://github.com/Drala-Mountain-Center-App/dmc_front_end/assets/115356592/e9d40706-7568-4b1f-ae80-4f07cd4f1f21" alt="login" width=30% />
  <img src="https://github.com/Drala-Mountain-Center-App/dmc_front_end/assets/115356592/4ce76c83-f745-4b43-bec7-e04e4ddd8ad1" alt="calendar" width=30% />
</div>
<!-- Table of Contents -->

# Table of Contents

- [About](#about)
- [Built With](#built-with)
- [Minimum Viable Product](#minimum-viable-product)
- [Possible Extensions](#possible-extensions)
- [Set up](#set-up)
- [Login Instructions](#login-instructions)
- [Wins](#wins)
- [Challenges](#challenges)
- [Wireframe](#wireframe)
- [GraphQL Fields](#graphql-fields)
 - [Queries and Mutations](#queries-and-mutations)
  - [List of queries](#list-of-queries)
  - [List of mutations](#list-of-mutations)
- [Schema](#schema)
- [Contributors](#contributors)


## About

The Drala Mountain Center App was made in association with [Drala Mountain Center](https://www.dralamountain.org/).
The App allows users to see scheduled programs, meditate with a meditation timer, view videos embeded in the app, view their meditation stats, view images of DMC, and donate to DMC via their website. <br>
The dmc_back_end application provides a single GraphQL endpoint with all app information. The team chose GraphQL for the simplicity of having a single endpoint with the capability to be flexible and efficient when handling queries from the front end application. The front end chose to React Native for faster development of mobile application.
</div>

### Built With:
[![ruby][ruby]][ruby-url]
[![rails][rails]][rails-url]
[![postgresql][postgresql]][postgresql-url]
[![javascript][javascript]][javascript-url]
[![react-native][react-native]][react-native-url]
[![heroku][heroku]][heroku-url]
[![graphql][graphql]][graphql-url]
[![expo][expo]][expo-url]

## Minimum Viable Product 
* Recreate the feel of Drala-Mounatain-Center's web application as a phone application.
* Create a link to Drala Mountain Center donation site, Network for Good within our application.
* Create a meditation timer page that provides user with a soothing experience while meditating.
* Database of DMC video talks, searchable, possibly using Vimeo.
* Import program calendar from DMC website backend.
* Integrate GraphQL as a stretch technology to facilitate API calls to our backend
* Integrate React Native as a stretch technology to prepare application for IOS deployment.

## Possible Extensions

* Login for user, to allow for statistics collection.
* User data collection displayed: "Here's your meditation habits, you've watched these videos".
* Randomized daily quotes from highly regarded figures linked to DMC or lojong slogans.
* Stripe/Auth.net/square for payment integration (likely prefer Stripe or something that can take apple/google pay, Paypal, Venmo, etc.
* Hosting on Android and Apple Store.
* AWS/Docker integration.
* Like/Love buttons/discussion boards for videos.
* Specific Advanced Practice Trackers (Ngondro/Stroke Practice).
* Integrate Web-sockets to add live chat feature.
* Add collaborative meditation option (using google meetup, facetime or other video app, not sure what the options are)

## Set up
1. Fork this repo
2. Clone the repo to your local machine
3. Go to the app store and install Xcode
4. Once you've installed, you should be able to type `npm i`, then `npm run ios` and open the ios simulator
5. Pick the simulator model of your choice in the xcode preferences, ie: iPhone 14
6. The simulator will reload when you make changes

## Login Instructions
You are able to use this app without logging in; however, to use functionality of storing and viewing personal meditation stats you can login with the following email address with any password at this stage of production:
- bobdylan@gmail.com
- loganlogan@gmail.com
- reid@gmail.com
- email@email.email

## Wins:
- Implementing our first app with React Native
- Successful collaboration as a cohesive 6-person full-stack team
- Agile work style embraced with efficiency and adaptability
- Achievement of Minimum Viable Product (MVP) and subsequent extensions
- Seamless integration of GraphQL and Apollo Client
- Animations with meditation timer/stats
  
## Challenges
- Overcoming cache policy challenges and troubleshooting Apollo Client errors
- Implementing Cypress end to end testing with React Native
- AsyncStorage for storing user information with mutation query's
- Learning curve with implementation of React Native, compatability and styling within components
  
## Wireframe

![wireframe](https://github.com/Drala-Mountain-Center-App/dmc_front_end/assets/115356592/c108f538-8916-48eb-a887-84256e8810eb)

## GraphQL Fields: 
* GraphQL endpoint: https://drala-mountain-api-4812ef039e59.herokuapp.com/graphql

### Queries and Mutations:
* Example Query:
```
query{
 allUsers {
   id
   firstName
   lastName
   email
   member
 }
}
```

* Example Mutation:
```
mutation {
    createMeditationByEmail(input: {
        totalSittingTime: 10,
        userEmail: "bobdylan@gmail.com"
    }){
        id
        totalSittingTime
        createdAt
        completedBy {
            id
            firstName
        }
    }
}
```
#### List of queries

##### User Queries
* queries: allUsers, user(id: user_id), userByEmail(email: "user_email")
* fields: id, firstName, lastName, email, member, totalMeditations, totalMeditationTime, averageMeditationTime

##### Video Queries
* queries: allVideos, videoById(id: video_id)
* fields: id, title, description, speaker, topic, length, dateRecorded, videoUrl, thumbnailUrl, embedCode, vimeoId

##### Program Queries
* query: allPrograms
* fields: name, startDate, endDate, content, image, price, url, registrationUrl, categories, teachers

#### List of mutations

##### User mutations
* Not yet available for public production use

##### Meditation mutations
* mutations: createMeditationByEmail(input: { totalSittingTime: Integer, userEmail: "String"
* available fields: id, totalSittingTime, createdAt, completedBy { any_user_field }

## Schema

<img src="https://github.com/Drala-Mountain-Center-App/dmc_back_end/assets/121198380/e634bdfe-e66a-473e-86c9-3691aa6f1748" alt="DMC Schema Image" width="90%">


## Contributors

* Reid Miller: [![Linkedin][linkedin]][reid-li-url] [![Github][Github]][reid-gh-url]
* Logan Cole: [![Linkedin][linkedin]][logan-li-url] [![Github][Github]][logan-gh-url]
* Alejandro Lopez: [![Linkedin][linkedin]][alejandro-li-url] [![Github][Github]][alejandro-gh-url]
* Sarah Moore: [![Linkedin][linkedin]][sarah-li-url] [![Github][Github]][sarah-gh-url]
* Sam McElhinney: [![Linkedin][linkedin]][sam-li-url] [![Github][Github]][sam-gh-url]
* Carol Bradsen: [![Linkedin][linkedin]][carol-li-url] [![Github][Github]][carol-gh-url]







<!-- MARKDOWN LINKS & IMAGES -->
<!--  -->
[contributors-shield]: https://img.shields.io/github/contributors/Drala-Mountain-Center-App/dmc_back_end.svg?style=for-the-badge
[contributors-url]: https://github.com/Drala-Mountain-Center-App/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/Drala-Mountain-Center-App/dmc_back_end.svg?style=for-the-badge
[forks-url]: https://github.com/Drala-Mountain-Center-App/dmc_back_end/network/members
[stars-shield]: https://img.shields.io/github/stars/Drala-Mountain-Center-App/dmc_back_end.svg?style=for-the-badge
[stars-url]: https://github.com/Drala-Mountain-Center-App/dmc_back_end/stargazers
[issues-shield]: https://img.shields.io/github/issues/Drala-Mountain-Center-App/dmc_back_end.svg?style=for-the-badge
[issues-url]: https://github.com/Drala-Mountain-Center-App/dmc_back_end/issues
[linkedin]: https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white
[logan-li-url]: https://www.linkedin.com/in/logan-cole-exasper
[reid-li-url]: https://www.linkedin.com/in/reid-miller-427377a4/
[alejandro-li-url]: https://www.linkedin.com/in/alejandrolopez1992/
[sam-li-url]: https://www.linkedin.com/in/samantha-mcelhinney/
[carol-li-url]: https://www.linkedin.com/in/carol-bradsen/
[sarah-li-url]: https://www.linkedin.com/in/sarah-moore-a35196127/
[ruby]: https://img.shields.io/badge/Ruby-CC342D?style=for-the-badge&logo=ruby&logoColor=white
[ruby-url]: https://www.ruby-lang.org/en/
[rails]: https://img.shields.io/badge/Ruby_on_Rails-CC0000?style=for-the-badge&logo=ruby-on-rails&logoColor=white
[rails-url]: https://rubyonrails.org/
[postgresql]: https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white/
[postgresql-url]: https://www.postgresql.org/docs/
[heroku]: https://img.shields.io/badge/Heroku-430098?style=for-the-badge&logo=heroku&logoColor=white
[heroku-url]: https://devcenter.heroku.com/articles/getting-started-with-rails7
[javascript]: https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black
[javascript-url]: https://developer.mozilla.org/en-US/docs/Web/JavaScript
[react-native]: https://img.shields.io/badge/React_Native-20232A?style=for-the-badge&logo=react&logoColor=61DAFB
[react-native-url]: https://reactnative.dev/docs/getting-started
[graphql]: https://img.shields.io/badge/-GraphQL-E10098?style=for-the-badge&logo=graphql&logoColor=white
[graphql-url]: https://graphql.org/
[expo]: https://img.shields.io/badge/expo-1C1E24?style=for-the-badge&logo=expo&logoColor=#D04A37
[expo-url]: https://docs.expo.dev/
[github]: https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white
[project-FE-url]: https://github.com/Drala-Mountain-Center-App/dmc_front_end
[project-BE-url]: https://github.com/Drala-Mountain-Center-App/dmc_back_end
[logan-gh-url]: https://github.com/exasperlnc
[alejandro-gh-url]: https://github.com/AlejandroLopez1992
[reid-gh-url]: https://github.com/reidsmiller
[sam-gh-url]: https://github.com/SamanthaMcElhinney
[carol-gh-url]: https://github.com/CBradsen
[sarah-gh-url]: https://github.com/sarahcatherine311
