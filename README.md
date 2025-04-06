🚗 Car Showroom - Web Application
Tech Stack: React + JavaScript + Tailwind CSS
📁 Project Structure
graphql
Copy
Edit
car-showroom/
│
├── public/
│   └── images/             # Car images, logo, etc.
│
├── src/
│   ├── assets/             # Static files like car data, icons
│   ├── components/         # Reusable UI components
│   ├── pages/              # Main pages (Home, CarDetails, etc.)
│   ├── App.js              # Main app routing and layout
│   ├── index.js            # React DOM rendering
│   └── styles/             # Tailwind config and custom styles
│
├── tailwind.config.js      # Tailwind configuration
├── postcss.config.js       # PostCSS setup for Tailwind
├── package.json            # Project dependencies
└── README.md               # Documentation
🔧 Installation & Setup
bash
Copy
Edit
git clone https://github.com/your-username/car-showroom.git
cd car-showroom

npm install
npm start
Ensure you have Node.js and npm installed.

🎨 Tailwind Setup
bash
Copy
Edit
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
Update tailwind.config.js:

js
Copy
Edit
module.exports = {
  content: ["./src/**/*.{js,jsx,ts,tsx}"],
  theme: {
    extend: {},
  },
  plugins: [],
}
Add Tailwind to index.css:

css
Copy
Edit
@tailwind base;
@tailwind components;
@tailwind utilities;
🧩 Key Components
1. CarCard.js
Displays individual car details (image, name, price).

jsx
Copy
Edit
const CarCard = ({ car }) => (
  <div className="bg-white shadow-md rounded-2xl p-4">
    <img src={car.image} alt={car.name} className="w-full h-48 object-cover rounded-xl" />
    <h2 className="text-xl font-semibold mt-2">{car.name}</h2>
    <p className="text-gray-500">{car.type}</p>
    <p className="text-indigo-600 font-bold">${car.price}</p>
  </div>
);
2. CarList.js
Displays a grid of all car cards.

jsx
Copy
Edit
import CarCard from './CarCard';

const CarList = ({ cars }) => (
  <div className="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6">
    {cars.map((car) => (
      <CarCard key={car.id} car={car} />
    ))}
  </div>
);
3. Navbar.js
jsx
Copy
Edit
const Navbar = () => (
  <nav className="bg-white shadow p-4 flex justify-between items-center">
    <h1 className="text-2xl font-bold text-indigo-600">Car Showroom</h1>
    <ul className="flex gap-4 text-gray-700">
      <li>Home</li>
      <li>Cars</li>
      <li>Contact</li>
    </ul>
  </nav>
);
🗂️ Pages
Home.js
jsx
Copy
Edit
import CarList from '../components/CarList';
import cars from '../assets/cars.json'; // Example car data

const Home = () => (
  <div className="p-6">
    <h2 className="text-3xl font-bold mb-4">Explore Our Collection</h2>
    <CarList cars={cars} />
  </div>
);
🛠️ Sample Car Data (cars.json)
json
Copy
Edit
[
  {
    "id": 1,
    "name": "Tesla Model S",
    "type": "Electric",
    "price": 79999,
    "image": "/images/tesla.jpg"
  },
  {
    "id": 2,
    "name": "BMW X5",
    "type": "SUV",
    "price": 65999,
    "image": "/images/bmw.jpg"
  }
]
✨ Styling Tips
Use Tailwind's grid/flex utilities for layout.

Add hover effects and transitions for car cards.

Mobile responsiveness is easy with sm:, md:, lg: variants.

Add a search or filter dropdown for better UX.

🚀 Optional Features
🚘 Car detail page with full specs

🔍 Search / filter by car type or price

💬 Contact form

🔐 User login (Firebase/Auth0)

🧪 Unit testing with Jest/React Testing Library

📸 Example UI (visual structure)
Navbar (top)

Hero section (optional)

Car cards grid (main content)

Footer (bottom)
