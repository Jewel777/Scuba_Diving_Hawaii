# 🌊 Scuba Diving Hawaii – Ruby on Rails Web App

A Ruby on Rails 7 application built to explore scuba diving experiences in Hawaii 🌴🐠.  
It allows users to browse dive locations, share posts with images, view popular galleries, and check seeded “See Details Location” data. The app also includes authentication, booking tours, and user interactions like comments & likes.

---

## 📦 Tech Stack

- **Ruby**: 3.1.2  
- **Rails**: 7.0.x (Importmap, Turbo, Stimulus)  
- **Database**: PostgreSQL  
- **Authentication**: Devise  
- **UI**: Bootstrap 5 + Bootswatch  
- **Forms**: bootstrap_form  
- **Search (optional)**: Ransack  
- **File Uploads**: Active Storage (local dev, easily switched to cloud like S3)  

---

## ✨ Features

- 👤 **Authentication**: Sign up, Sign in, Sign out with Devise  
- 📍 **Locations**: Browse, view, create new scuba diving locations  
- 📑 **Request Locations**: Submit new location requests via a form  
- 📷 **Posts**: Create posts with images (via Active Storage), edit/delete your own posts  
- ❤️ **Likes & Comments**: Interact with posts using likes and comments  
- 🖼️ **Popular Photos**: Static gallery page with hover zoom  
- 📚 **See Details Locations**: Tabular list view populated with seeded sample data  
- 🛥️ **Bookings**: Book scuba diving tours linked to locations  
- 👨‍🏫 **Guides vs Divers**: Differentiated by `certified` boolean in users table  

---

## 🗂️ Project Structure Highlights

app/
├── controllers/
│ ├── locations_controller.rb
│ ├── posts_controller.rb
│ └── pages_controller.rb
├── models/
│ └── see_details_location.rb
└── views/
├── layouts/application.html.erb
├── locations/
│ ├── request_location.html.erb
│ └── see_details_location.html.erb
└── pages/
├── popular_photos.html.erb
├── pic_details.html.erb
└── see_details.html.erb
config/
├── routes.rb
db/
├── migrate/XXXXXXXXXXXXXX_create_see_details_locations.rb
├── schema.rb
└── seeds.rb

yaml
Copy
Edit

---

## ⚙️ Setup Instructions

Clone the repository and set up locally:

```bash
# 1. Clone the repo
git clone https://github.com/<your-username>/Scuba_Diving_Hawaii.git
cd Scuba_Diving_Hawaii

# 2. Install dependencies
bundle install

# 3. Setup database
bin/rails db:create db:migrate db:seed

# 4. Start the server
bin/rails s
Visit: http://localhost:3000

🧪 Seed Data
The db/seeds.rb file provides demo data for quick testing:

👥 Users (Alice, Bob, etc.)

📍 Locations (e.g., Maui – Black Rock, Molokini Wall)

📸 Posts (with sample images like 1.jpeg, 2.jpeg)

💬 Comments & Likes

📚 SeeDetailsLocation (tabular seeded records with names, years, and details)

Run seeds with:

bash
Copy
Edit
bin/rails db:seed
🚏 Key Routes
/ → redirects to /home (Pages#index)

/locations → browse all locations

/request_location → form to request a new location

/see_details_location → list seeded location details

/posts → user posts (CRUD)

/popular_photos → static photo gallery

/pic_details → scuba photo stories

/see_details → grid of sample shared pictures

/users/sign_in & /users/sign_up → Devise authentication
