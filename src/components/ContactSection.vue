<template>
  <div
    class="container row d-flex mx-auto justify-content-center pt-5 mt-5 mb-4"
  >
    <h1
      class="display-1"
      data-aos="fade-left"
      data-aos-anchor-placement="top-bottom"
      data-aos-delay="index * 1000"
    >
      Reach Me
    </h1>
    <div
      class="contact-form col-md-6 m-auto p-2 mb-4"
      data-aos="fade-right"
      data-aos-anchor-placement="top-bottom"
      data-aos-delay="index * 1000"
    >
      <form
        action="https://formspree.io/f/mayrkyyb"
        target="_blank"
        method="POST"
      >
        <h4 class="mt-2">
          Please fill out the form below if you'd like more information
        </h4>
        <div class="form-group">
          <label for="name">Your Name</label>
          <input
            name="name"
            type="text"
            class="form-control"
            id="name"
            placeholder="Enter your name"
            required
          />
        </div>
        <div class="form-group mt-2">
          <label for="email">Your Email</label>
          <input
            name="email"
            type="email"
            class="form-control"
            id="email"
            placeholder="Enter your email"
            required
          />
        </div>
        <div class="form-group mt-2">
          <label for="message">Message</label>
          <textarea
            name="message"
            class="form-control"
            id="message"
            rows="3"
            placeholder="Enter your message"
            required
          ></textarea>
        </div>
        <div class="m-3 button-group">
          <button type="submit" class="btn pink-border">Submit</button>
          <button type="reset" class="btn pink-border">Clear</button>
        </div>
      </form>
    </div>
    <div
      class="contact-card col-md-6 m-auto p-2"
      data-aos="fade-left"
      data-aos-anchor-placement="top-bottom"
      data-aos-delay="index * 1000"
    >
      <h2>Get in touch with me</h2>
      <p><strong>Name:</strong> Nicki S Abels</p>
      <p><strong>Email:</strong> nickisabels73@gmail.com</p>
      <p><strong>Phone:</strong> 067 775 8935</p>
      <p><strong>Location:</strong> Retreat, Cape Town</p>

      <ul class="social-icons">
        <a
          href="https://github.com/NickiSamantha"
          class="btn pink-border"
          target="_blank"
        >
          <i class="fa-brands fa-github"></i
        ></a>
        <a
          href="https://www.linkedin.com/in/nicki-samantha-abels/"
          class="btn pink-border"
          target="_blank"
        >
          <i class="fab fa-linkedin-in"></i
        ></a>
      </ul>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.btn {
  margin: 5px;
  padding: 10px 20px;
  border: 1px solid #ff69b4;
  color: #ff69b4;
  background-color: transparent;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
}

.btn:hover {
  background-color: #ff69b4;
  color: white;
}
.button-group {
  display: flex;
  justify-content: space-between;
}
.contact-form {
  max-width: 31.25rem;
  margin: 3.125rem auto;
  padding: 1.875rem;
  border: 1px solid pink;
  border-radius: 0.5rem;
  background: #fdeeed;
  font-family: "Playfair Display", serif;
}
.contact-card {
  max-width: 25rem;
  margin: 3.125rem auto;
  padding: 1.875rem;
  border-radius: 0.5rem;
  border: 1px solid pink;
  background: #fdeeed;
}
.social-icons {
  list-style: none;
  padding: 0;
}

.social-icons li {
  display: inline-block;
  margin-right: 0.625;
}
</style>
