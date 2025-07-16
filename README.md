<!DOCTYPE html>
<html lang="en">
<head>
    <!-- AOS CSS -->
<link href="https://unpkg.com/aos@2.3.1/dist/aos.css" rel="stylesheet">

    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
  <img src="sky-high van.jpg">
    <div class="Menu">
        <div class="logo">Sky High</div>
        <div class="hamburger" onclick="toggleMenu()">☰</div>
        <ul id="nav-links">
          <li><a href="#home">Home</a></li>
          <li><a href="#about">About Us</a></li>
          <li><a href="#services">Services</a></li>
          <li><a href="#track">Track Shipment</a></li>
          <li><a href="#request">Request Pickup</a></li>
          <li><a href="#faq">FAQs</a></li>
          <li><a href="#contact">Contact</a></li>
          <li><a href="#blog">Blog</a></li>
        </ul>
      </div>
      
      <section id="home" data-aos="fade-up">
          <h1 data-aos="zoom-in">Sky High Logistics</h1>
          <p>We Deliver Above & Beyond</p>
          <button onclick="document.getElementById('track').scrollIntoView();">Track Your Package</button>
          <button onclick="document.getElementById('request').scrollIntoView();">Request Pickup</button>
          <div class="highlights">
            <p>Fast, Reliable & Secure Deliveries</p>
            <p>Nationwide & International Coverage</p>
          </div>
          <div class="testimonials">
            <blockquote>Excellent service! My package arrived ahead of schedule. – Happy Client</blockquote>
          </div>
        </section>

        <!--Tracking-->
      <section id="track" data-aos="zoom-in">
          <h2>Track Your Shipment</h2>
          <form onsubmit="trackPackage(event)">
            <input type="text" id="trackingId" placeholder="Enter Tracking ID" required>
            <button data-aos="fade-up" data-aos-delay="200">Track</button>
          </form>
          <div id="trackingResult"></div>
        </section>
         <!-- Services -->
      <section id="services" data-aos="fade-left">
        <img src="sky-high van.png" alt="">
          <h2>Our Services</h2>
          <ul>
            <li>Local Delivery</li>
            <li>International Shipping</li>
            <li>Same-Day Express</li>
            <li>E-commerce Integration</li>
            <li>Warehousing & Fulfillment</li>
          </ul>
        </section>
         <!-- Contact -->
      <section id="contact" data-aos="fade-up">
          <h2>Contact Us</h2>
          <form id="contactForm">
            <input type="text" id="name" placeholder="Your Name" required>
            <input type="email" id="email" placeholder="Your Email" required>
            <textarea id="message" placeholder="Your Message" required></textarea>
            <button type="submit">Send Message</button>
          </form>
          <div id="formResponse"></div>          
        </section>
         <!-- FAQs -->
      <section id="faq" data-aos="fade-down">
          <h2>FAQs</h2>
          <p><strong>Q:</strong> How long does delivery take?</p>
          <p><strong>A:</strong> It depends on location and service type. Same-day and next-day options available.</p>
        </section>
         <!-- About Us -->
      <section id="about" data-aos="fade-right">
          <h2>About Us</h2>
          <p>At Sky High Logistics, we take your deliveries to new heights. With a passion for precision and a commitment to speed, we offer reliable courier and logistics solutions that keep your world moving.</p>
          <p>Since our inception, we've dedicated ourselves to bridging distances, empowering businesses, and delivering smiles one package at a time.</p>
          <p>Whether it’s an urgent document or bulk logistics, Sky High gets it there safely, swiftly, and securely.</p>

        </section>
         <!-- Blog -->
      <section id="blog" data-aos="flip-up">
          <h2>Logistics Tips & News</h2>
          <ul>
            <li><a href="#">5 Things to Know Before Shipping Internationally</a></li>
            <li><a href="#">How to Track Your Delivery in Real-Time</a></li>
            <li><a href="#">Same-Day Delivery: What Businesses Need to Know</a></li>
          </ul>
        </section>
        <footer class="site-footer">
          <div class="footer-container">
            <div class="footer-brand">
              <h3>Sky High Logistics</h3>
              <p>Delivering above & beyond — locally and globally.</p>
            </div>
        
            <div class="footer-links">
              <h4>Quick Links</h4>
              <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About Us</a></li>
                <li><a href="#services">Services</a></li>
                <li><a href="#track">Track</a></li>
                <li><a href="#contact">Contact</a></li>
              </ul>
            </div>
        
            <div class="footer-contact">
              <h4>Contact Info</h4>
              <p>Email: info@skyhcourier.com</p>
              <p>Phone: +234 XXX XXX XXXX</p>
            </div>
        
            <div class="footer-social">
              <h4>Follow Us</h4>
              <a href="#"><img src="https://cdn-icons-png.flaticon.com/24/733/733547.png" alt="Facebook"></a>
              <a href="#"><img src="https://cdn-icons-png.flaticon.com/24/733/733579.png" alt="Twitter"></a>
              <a href="#"><img src="https://cdn-icons-png.flaticon.com/24/733/733558.png" alt="Instagram"></a>
            </div>
          </div>
        
          <div class="footer-bottom">
            <p>&copy; 2025 Sky High Logistics. All rights reserved.</p>
          </div>
        </footer>
        </main>
     <footer>
        <p>&copy; 2025 Sky High Logistic. All rights reserved.</p>
      </footer>
      <!-- AOS JS -->
<script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
<script>
  AOS.init({
    duration: 1000, // animation duration in ms
    once: true      // animate only once when scrolled into view
  });
</script>
<script>
    document.getElementById('contactForm').addEventListener('submit', async function (e) {
      e.preventDefault();
  
      const name = document.getElementById('name').value;
      const email = document.getElementById('email').value;
      const message = document.getElementById('message').value;
  
      try {
        const res = await fetch('http://localhost:5000/contact', {
          method: 'POST',
          headers: { 'Content-Type': 'application/json' },
          body: JSON.stringify({ name, email, message })
        });
  
        const data = await res.json();
        document.getElementById('formResponse').innerText = data.message;
      } catch (error) {
        document.getElementById('formResponse').innerText = 'Failed to send message.';
      }
    });
  </script>  
     </body>
    </html>
  
