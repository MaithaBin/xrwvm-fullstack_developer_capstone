# Overview
This project was provided by the Full Stack Application Development Capstone Project course in Coursera. The project templete was forked from the following GitHub repository, and contaiened the main Django application and a skeleton structure of the front-end and back-end. The course was divided into 5 modules to create a full stack application.

### Template
[xrwvm-fullstack_developer_capstone](https://github.com/ibm-developer-skills-network/xrwvm-fullstack_developer_capstone)

### Architecture
![v2 capstone-dealership-architecture](https://github.com/MaithaBin/xrwvm-fullstack_developer_capstone/assets/141325017/7448715d-f340-4701-b08d-a4160200e0b1)

### Languages/Frameworks/Libraries
- HTML/CSS/Boostrap
- Javascript
- React
- Node.js
- Express
- Python
- Django
- Flask

### Databases
- MongoDB
- SQlite

# Module 1
Module 1 was simply to add static page such as "About Us" page and "Contact Us" using HTML/CSS/Boostrap and run the Djapngo app on the deployment server. I downloaded images, added some text, and styled the pages.

![about_us](https://github.com/MaithaBin/xrwvm-fullstack_developer_capstone/assets/141325017/ae0dc0a7-2055-48fa-b07b-31a465ce9ad4)
![contact_us](https://github.com/MaithaBin/xrwvm-fullstack_developer_capstone/assets/141325017/67df70b8-e344-4a92-9fcf-05bac61891b3)


# Module 2
This module was to create the user management system to allow users to register, login, and logout using React. The templete provided some build-in user management services to me. The tasks were to add the pathes to recoginize the front-end to Django app, to handle with a login/logout/register request, and to add register function.

![login](https://github.com/MaithaBin/xrwvm-fullstack_developer_capstone/assets/141325017/ce308e0a-cdc0-4e98-842e-8e7263df6822)
![logout](https://github.com/MaithaBin/xrwvm-fullstack_developer_capstone/assets/141325017/ac0405ff-befe-4feb-901d-b30d5a68f767)
![sign-up](https://github.com/MaithaBin/xrwvm-fullstack_developer_capstone/assets/141325017/479126cc-8fe9-4b56-85eb-a590ecc337e1)

# Module 3
In this module, there were the following tasks given: creating some API endpoints using Express and MongoDB, building CarModel and CarMake Django Model, and creating Django Proxy Services Of Backend APIs.

The template provided me two schema files for Reviews and Dealerships entities, along with JSON files containing dealership and review data to be loaded into MongoDB and served through endpoints. The Node app uses mongoose to interact with the MongoDB. The first task was to implement API endopoints in server/database/app.js. After implementing, the code can fetch dealers and to filter them by state or ID.
![dealer_review](https://github.com/MaithaBin/xrwvm-fullstack_developer_capstone/assets/141325017/1ecb0d7e-08ad-4a32-8e06-3aca62aaff57)
![dealerships](https://github.com/MaithaBin/xrwvm-fullstack_developer_capstone/assets/141325017/1c68d36e-2f4d-417a-ba79-64c052d21efd)
![dealer_details](https://github.com/MaithaBin/xrwvm-fullstack_developer_capstone/assets/141325017/901bc7cc-3f1b-4c70-b172-77d36185527d)
![kansasDealers](https://github.com/MaithaBin/xrwvm-fullstack_developer_capstone/assets/141325017/8387f8d9-acce-4216-a567-45b3566012f7)
 
Next, the task was to create 2 models: CarModel and CarMake. The former was a model to save some data about a car's model, while the latter was to save some data about a car's make. After implementing the 2 models, I registered the CarMake and CarModel models with the admin site.
![admin_logout2](https://github.com/MaithaBin/xrwvm-fullstack_developer_capstone/assets/141325017/c5c5230c-9525-4274-b45e-13a3ef17c724)
![cars](https://github.com/MaithaBin/xrwvm-fullstack_developer_capstone/assets/141325017/72c58881-1fef-4838-8411-8396bcffa1d0)
![car models](https://github.com/MaithaBin/xrwvm-fullstack_developer_capstone/assets/141325017/0f3ebf88-42ef-46e8-aa93-7702400a5e1f)

Finally, the task was to create such Django views as proxy services. To integrate external dealer and review data, I needed to call the API end points from the Django app and process the API results in Django views. Such Django views can be seen as proxy services to the end user because they fetch data from external resources per users' requests. 

I added the get_request method to access API endpoints to fetchReviews and fetchDealers from the Django app in djangoapp/restapis.py. The get_request method has two arguments, the endpoint to be requested, and a Python keyword arguments representing all URL parameters to be associated with the get call. This function calls GET method in requests library with a URL and any URL parameters such as dealerId.

Also, I deployed sentiment analysis on Code Engine as a microservice. The template provided sentiment_analyzer.py which uses NLTK for sentiment analysis and a Dockerfile for deploying the service in Code Engine and consuming it as a microservice.

To Django views to get dealers, I updated get_dealerships view method and add get_dealer_details and get_dealer_reviews method in djangoapp/views.py. Plus, to create a Django view to post a dealer review, post_review method was added in restapis.py and a new def add_review(request): method was created in views.py to handle review post request.

# Module 4
Module 4 was to add dynamic front end pages using React. I added the Dealers component in frontend/src/App.js and the routes for Dealers and Dealer in server/djangoproj/urls.py. 
![get_dealers_loggedin](https://github.com/MaithaBin/xrwvm-fullstack_developer_capstone/assets/141325017/215da9f6-c0e2-4727-a7ee-294dcbcc1340)
![dealersbystate](https://github.com/MaithaBin/xrwvm-fullstack_developer_capstone/assets/141325017/f00b9d06-9d3d-491e-b391-bc789993f3ca)

I also imported the route to the Dealer REACT component to the rest of the routes to show reviews. 
![dealer_id_reviews](https://github.com/MaithaBin/xrwvm-fullstack_developer_capstone/assets/141325017/2639ba18-0d64-445a-aa3c-c63817b027f1)

In addition, to create a dealer details or reviews page, I Imported PostReview component and added postreview/<dealer id> route to frontend/src/App.js.
![dealership_review_submission](https://github.com/MaithaBin/xrwvm-fullstack_developer_capstone/assets/141325017/ba5cfb4f-be89-4d69-9dd5-81f8acdc0419)
![added_review](https://github.com/MaithaBin/xrwvm-fullstack_developer_capstone/assets/141325017/1bcb3f43-416e-431f-be13-203fcceb8e67)

# Module 5
In this module. the task was to set a CI/CD action flow for linting all the JS and Python files I have created. A workflow that would lint my Python and JavaScript files was provided, so I copied into GitHub Actions. When running it, I got over 200 lint errors. Then I fixed my code and eventually removed all lint errors.
![CICD](https://github.com/MaithaBin/xrwvm-fullstack_developer_capstone/assets/141325017/734b7ee0-db3f-4c06-9839-14cdd98e191a)



