+++++++++++++++ NOTES +++++++++++++++

<!-- React-Ecommerce-website -->

1.) create new project
  npm create vite@latest

cd react-ecommerce-website
  npm install
  npm run dev

2.) react-router-dom important website with documentation.
  https://reactrouter.com/6.28.0/start/tutorial

3.) install react-router dom package in your project
  npm install react-router-dom
  npm install react-router-dom localforage match-sorter sort-by

4.) go to main.jsx file and paste everything here.

import {
  createBrowserRouter,
  RouterProvider,
} from "react-router-dom";


const router = createBrowserRouter([
  {
    path: "/",
    element: <App/>,
  },
]);

createRoot(document.getElementById('root')).render(
  <RouterProvider router={router} />
)

5.) go to index.css file and delete old css in that file
and app.css file also delete old css

6.) Bootstrap setup in this file.
  npm i bootstrap@5.3.3

7.) React bootstrap set up in your project
  npm install react-bootstrap bootstrap

8.) install package reactcounter up in your project
  npm i react-countup
  Qs. what is benefit of react counterup package
  displaying statistics or scores that change over time, offering options for duration, easing, and formatting.

The react-counterup package simplifies creating animated number counters in React projects. Key benefits:

Engaging UI: Adds dynamic visuals for metrics or statistics.
Easy to Use: Minimal code for professional animations.
Customizable: Supports duration, easing effects, and start/end values.
Lightweight: Adds minimal overhead to your app.
Responsive: Works well on all devices.
Time-Saving: Eliminates the need for custom counter logic.

9.) install swiper.js
  npm install swiper

  The SwiperJS package is a powerful tool for implementing touch-friendly sliders and carousels in React projects
  1. Feature-Rich
    SwiperJS offers advanced features like:

    Responsive sliders: Automatically adapt to different screen sizes.
    Touch and gesture support: Swipe navigation for mobile and touch devices.
    Lazy loading: Loads images only when needed, improving performance.
    Infinite looping: Seamless carousel looping for better user experience.

10.) install proper.js
  npm i popper.js

  Installing the Popper.js package in your React project provides a powerful and reliable way to manage tooltips, popovers, and dropdowns. Here are the key benefits:

Installing the Popper.js package in your React project provides a powerful and reliable way to manage tooltips, popovers, and dropdowns. Here are the key benefits:

1. Precise Positioning
Popper.js ensures accurate placement of elements, even in complex layouts or when dealing with edge cases like scrolling or resizing.

2. Dynamic Updates
It automatically recalculates positions when the target or viewport changes, ensuring elements stay correctly aligned.

3. Easy Integration
Works seamlessly with React libraries like @popperjs/core and UI frameworks (e.g., Bootstrap, Material-UI) to handle positioning logic without custom code.

4. Highly Customizable
Offers options to configure:

Placement (top, bottom, left, right, etc.).
Offsets, margins, and boundaries.
Adaptive behaviors like flipping or preventing overflow.
5. Lightweight and Performant
Optimized for performance with minimal impact on your application's speed.

6. Supports Complex Scenarios
Handles advanced use cases like nested scrolling containers, dynamic content, and responsive popups.

Common Use Cases
Tooltips: Position descriptive text on hover or focus.
Dropdowns: Align menus with buttons or icons.
Modals and Popovers: Manage contextual overlays in your app.


11.) add projects images with the help of gitubh.

12.) go to main.jsx and import that packages

// ## 1. Connect CSS & JS file to main.jsx file
import 'swiper/css';

// **/_ bootstrap css _/**
import 'bootstrap/dist/css/bootstrap.min.css';
import 'bootstrap/dist/js/bootstrap.min.js'

// **/_ fonts and icons _/**
import '././assets/css/icofont.min.css';
import '././assets/css/animate.css'
import '././assets/css/style.min.css';

13.) go to public folder and paste favicon.icon here

14.) go to index.html file and change this two thing in your project.
   <link rel="icon" type="image/svg+xml" href="/favicon.ico" />
   <title>E-commerce Website using React JS</title>

15.) go to App.jsx file and check some property of bootstrap its work properly or not
  1.) 'text-primary' to give big size of font
  <h1 className='text-primary'>Hello, React Developers!!!</h1>

  2.) 'text-primary fs-4' to give small size of font
  <h1 className='text-primary fs-4'>Hello, React Developers!!!</h1>

  3.) 'text-primary m-5' to give margin.
  <h1 className='text-primary m-5'>Hello, React Developers!!!</h1>

  4.) 'text-primary pt-3' to give padding top
  <h1 className='text-primary pt-3'>Hello, React Developers!!!</h1>

  5.) 'text-primary pt-3' to give padding bottom
  <h1 className='text-primary pb-3'>Hello, React Developers!!!</h1>

16.) go to src folder and src folder inside create home folder and home folder inside Home.jsx file
src folder/home folder /Home.jsx

import React from 'react'

const Home = () => {
  return (
    <div>Home</div>
  )
}

export default Home

17.) go to main.jsx file and do some change.
  import Home from "./home/Home.jsx";
  import Blog from "./blog/Blog.jsx";

const router = createBrowserRouter([
  {
    path: "/",
    element: <App />,
    children: [
      {path: "/", element: <Home />},
      {path: "/blog", element: <Blog />},
    ]
  },
]);

18.) go to App.jsx
  import { Outlet } from 'react-router-dom'

   return (
    <>
      <nav>Nav bar</nav>
      <Outlet />
    </nav>
  )

19.) go to src folder and create blog folder and blog folder inside create Blog.jsx

import React from 'react'

const Blog = () => {
  return (
    <div>Blog</div>
  )
}

export default Blog;

20.) go to main.jsx file and do some change.
  import Home from "./home/Home.jsx";
  import Blog from "./blog/Blog.jsx";

const router = createBrowserRouter([
  {
    path: "/",
    element: <App />,
    children: [
      {path: "/", element: <Home />},
      {path: "/blog", element: <Blog />},
    ]
  },
]);

21.) go to src folder and create components folder and components create file NavItems.jsx
src folder/ components folder/ NavItems.jsx

import React from 'react'

const NavItems = () => {
  return (
    <div>NavItems</div>
  )
}

export default NavItems;

22.) go to App.jsx file and import NavItems and put inside fregment
  import NavItems from './components/NavItems'

   return (
    <>
      <NavItems />
      <Outlet />
    </>
  )

23.) Design Navbar 
  go to NavItems.jsx

  const NavItems = () => {
  const [menuToggle, setMenuToggle] = useState(false);
  const [socialToggle, setSocialToggle] = useState(false);
  const [headerFixed, setHeaderFixed] = useState(false);

  // Logic with Header fixed
  // addevent listener
  window.addEventListener("scroll", () => {
    if (window.scrollY > 200) {
      setHeaderFixed(true);
    } else {
      setHeaderFixed(false);
    }
  });

  return (
    <header
      className={`header-section style-4 ${
        headerFixed ? "header-fixed fadeInUp" : ""
      }`}
    >
      {/* header top start here */}
      <div className={`header-top d-md-none ${socialToggle ? "open" : ""}`}>
        <div className="container">
          <div className="header-top-area">
            <Link to="/signup" className="lab-btn me-3">
              <span>Create Account</span>
            </Link>
            <Link to="/login">Log in</Link>
          </div>
        </div>
      </div>

      {/* header bottom start here */}
      <div className="header-bottom">
        <div className="container">
          <div className="header-wrapper">
            {/* logo */}
            <div className="logo-search-acte">
              <div className="logo">
                <Link to={"/"}>
                  <img src={logo} alt="" />
                </Link>
              </div>
            </div>
            {/* menu area */}
            <div className="menu-area">
              <div className="menu">
                <ul className={`lab-ul ${menuToggle ? "active" : ""}`}>
                  <li>
                    <Link to="/">Home</Link>
                  </li>
                  <li>
                    <Link to="/shop">Shop</Link>
                  </li>
                  <li>
                    <Link to="/blog">Blog</Link>
                  </li>
                  <li>
                    <Link to="/about">About</Link>
                  </li>
                  <li>
                    <Link to="/contact">Contact</Link>
                  </li>
                </ul>
              </div>

              {/* sign in & log in */}
              <Link to="/sign-up" className="lab-btn me-3 d-none  d-md-block">
                Create Account
              </Link>
              <Link to="/login" className="d-none d-md-block">
                Log In
              </Link>

              {/* menu Toggler */}
                <div onClick={() => setMenuToggle(!menuToggle)} className={`header-bar d-lg-none ${menuToggle ? "active" : ""}`}>
                  <span></span>
                  <span></span>
                  <span></span>
                </div>

              {/* social Toggler */}
              <div className="ellepsis-bar d-md-none" onClick={() => setSocialToggle(!socialToggle)}>
              <i className="icofont-info-square"></i>
              </div>
            </div>
          </div>
        </div>
      </div>
    </header>
  );
};

export default NavItems;



24.) take icon in this website:-
  https://icofont.com/

25.) Design Banner in your website:-
  go to home folder and create Banner.jsx file

import React from 'react'

const Banner = () => {
  return (
    <div>Banner</div>
  )
}

export default Banner;

26.) go to Home.jsx file
  import Banner from './Banner';

   return (
    <div>
      <Banner />
    </div>
  )

27.) go to Banner.jsx

import React, { useState } from "react";
import productData from "../products.json";
import { Link } from "react-router-dom";

const title = (
  <h2>
    Search Your One From <span>Thousand</span> of Products
  </h2>
);
const desc = "We have the largest collection of products";
const bannerList = [
  {
    iconName: "icofont-users-alt-4",
    text: "1.5 Million Customers",
  },
  {
    iconName: "icofont-notification",
    text: "More then 2000 Marchent",
  },
  {
    iconName: "icofont-globe",
    text: "Buy Anything Online",
  },
];

const Banner = () => {
  const [searchInput, setSearchInput] = useState("");
  const [filteredProducts, setfilteredProducts] = useState(productData);
  // console.log(productData);

  // search funtionality
  const handleSearch = (e) => {
    const searchTerm = e.target.value;
    setSearchInput(searchTerm);

    // filtering products based on search
    const filtered = productData.filter((product) =>
      product.name.toLowerCase().includes(searchTerm.toLowerCase())
    );

    setfilteredProducts(filtered);
  };

  return (
    <div className="banner-section style-4">
      <div className="container">
        <div className="banner-content">
          {title}
          <form>
            <input
              type="text"
              name="search"
              id="search"
              placeholder="Search your product"
              value={searchInput}
              onChange={handleSearch}/>
            <button type="submit">
            <i className="icofont-search"></i>
            </button>
          </form>
          <p>{desc}</p>
          <ul className="lab-ul">
            {searchInput &&
              filteredProducts.map((product, i) => (
                <li key={i}>
                  <Link to={`/shop/${product.id}`}>{product.name}</Link>
                </li>
              ))}
          </ul>
        </div>
      </div>
    </div>
  );
};

export default Banner;

28.) go to components folder and create SelectedCategory.jsx file

import React from "react";

const SelectedCategory = (select) => {
  return (
    <select>
      <option value="all">All Categories</option>
      <option value="electronics">Electronics</option>
      <option value="computer">Computer</option>
      <option value="smart-home">Smart Home</option>
      <option value="automotive">Automotive</option>
      <option value="baby">Baby</option>
      <option value="beauty">Beauty</option>
      <option value="personal-care">Personal Care</option>
      <option value="butcher-shop">Butcher Shop</option>
      <option value="cafe">Cafe</option>
      <option value="charity-2">Charity</option>
      <option value="church">Church</option>
      <option value="clinic">clinic</option>
      <option value="college">College</option>
      <option value="conference">Conference</option>
      <option value="construction">Construction</option>
      <option value="corona-virus">Corona Virus</option>
      <option value="corporate">Corporate</option>
      <option value="covid19">Covid19</option>
      <option value="digital-products">Digital Products</option>
      <option value="doctors">doctors</option>
      <option value="ecological">Ecological</option>
      <option value="education">Education</option>
      <option value="entertainment">Entertainment</option>
      <option value="environment">Environment</option>
      <option value="environmental">Environmental</option>
      <option value="events">Events</option>
      <option value="fitness">Fitness</option>
      <option value="food-shop">Food Shop</option>
      <option value="free">Free</option>
      <option value="gym">Gym</option>
      <option value="halloween">Halloween</option>
      <option value="health">health</option>
      <option value="healthcare">healthcare</option>
      <option value="learnpress">learnpress</option>
      <option value="meat-shop">Meat Shop</option>
      <option value="medical">medical</option>
      <option value="medical-prevention">Medical Prevention</option>
      <option value="meetup">Meetup</option>
      <option value="mobile-apps">Mobile Apps</option>
      <option value="music">Music</option>
      <option value="news">News</option>
      <option value="nonprofit">Nonprofit</option>
      <option value="onepage">Onepage</option>
      <option value="online-course">Online Course</option>
      <option value="personal-blog">Personal Blog</option>
      <option value="portfolio">Portfolio</option>
      <option value="pregnancy">pregnancy</option>
      <option value="premium">premium</option>
      <option value="psd">psd</option>
      <option value="religion">Religion</option>
      <option value="restaurants">Restaurants</option>
      <option value="school">School</option>
      <option value="seo">SEO</option>
      <option value="software">Software</option>
      <option value="startups">Startups</option>
      <option value="university">University</option>
      <option value="vcard">Vcard</option>
      <option value="woocommerce">WooCommerce</option>
      <option value="yoga">Yoga</option>
      <option value="magazine">Magazine</option>
      <option value="event-wordpress">Event</option>
    </select>
  );
};

export default SelectedCategory;

29.) again go to Banner.jsx file and create all product list in form tag
in the starting.
<form>
  <SelectedCategory select={"all"} />
</form>

30.) go to home folder inside create HomeCategory.jsx file

import React from "react";
import { Link } from "react-router-dom";

const subTitle = "Choose Any Products";
const title = "Buy Everything with Us";
const btnText = "Get Started Now";

const categoryList = [
  {
    imgUrl: "src/assets/images/category/01.jpg",
    imgAlt: "category rajibraj91 rajibraj",
    iconName: "icofont-brand-windows",
    title: "DSLR Camera",
  },
  {
    imgUrl: "src/assets/images/category/02.jpg",
    imgAlt: "category rajibraj91 rajibraj",
    iconName: "icofont-brand-windows",
    title: "Shoes",
  },
  {
    imgUrl: "src/assets/images/category/03.jpg",
    imgAlt: "category rajibraj91 rajibraj",
    iconName: "icofont-brand-windows",
    title: "Photography",
  },
  {
    imgUrl: "src/assets/images/category/04.jpg",
    imgAlt: "category rajibraj91 rajibraj",
    iconName: "icofont-brand-windows",
    title: "Formal Dress",
  },
  {
    imgUrl: "src/assets/images/category/05.jpg",
    imgAlt: "category rajibraj91 rajibraj",
    iconName: "icofont-brand-windows",
    title: "Colorful Bags",
  },
  {
    imgUrl: "src/assets/images/category/06.jpg",
    imgAlt: "category rajibraj91 rajibraj",
    iconName: "icofont-brand-windows",
    title: "Home Decor",
  },
];

const HomeCategory = () => {
  return <div className="category-section style-4 padding-tb">
      <div className="container-">
        {/* section header */}
        <div className="section-header text-center">
          <span className="subtitle">{subTitle}</span>
          <h2 className="title">{title}</h2>
        </div>

        {/* section card */}
        <div className="section-wrapper">
          <div className="row g-4 justify-content-center row-cols-md-3 row-cols-sm-2 row-cols-1">
            {
              categoryList.map((val, i) => (<div key={i} className="col">
                <Link to="/shop" className="category-item">
                  <div className="category-inner">

                    {/* image thumbnail */}
                    <div className="category-thumb">
                      <img src={val.imgUrl} alt="" />
                    </div>

                    {/* content  */}
                    <div className="category-content">
                      <div className="cate-icon">
                        <i className={val.iconName}></i>
                      </div>
                      <Link to="/shop"><h6>{val.title}</h6></Link>
                    </div>


                  </div>
                </Link>
              </div>))
            }
          </div>
          <div className="text-center mt-5">
            <Link to="/shop" className="lab-btn"><span>{btnText}</span></Link>
          </div>
        </div>
      </div>
  </div>;
};

export default HomeCategory;


31.) go to home folder and create CategoryShowCase.jsx file

32.) go to Home.jsx file
  import CategoryShowCase from './CategoryShowCase';

const Home = () => {
  return (
    <div>
      <Banner />
      <HomeCategory />
      <CategoryShowCase />
    </div>
  )
}

33.) 






