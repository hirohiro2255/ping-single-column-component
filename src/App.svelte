<script>
  let email = '';
  let isError = false;
  let errorMsg = '';

  function validateEmail(email) {
    if (/^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/.test(email)) {
      return true;
    }
    return false;
  }

  function handleClick() {
    if (email.length === 0) {
      errorMsg = 'Email cannot be empty';
      isError = true;
    } else if (validateEmail(email)) {
      email = '';
      isError = false;
      errorMsg = '';
    } else {
      isError = true;
      errorMsg = 'Please provide a valid email address';
    }
  }
</script>

<main class="container">
  <section class="hero-container">
    <div class="hero-group">
      <h1 class="primary-heading">PING<small class="dot">.</small></h1>
      <h2 class="secondary-heading">We are launching <strong>soon!</strong></h2>
      <p class="paragraph">Subscribe and get notified</p>
    </div>
    <div class="interaction-group">
      <div class="input-group">
        <input
          bind:value={email}
          type="email"
          class="email"
          class:error={isError}
          placeholder="Your email address"
        />
        <small class="error-msg" class:errorVisible={isError}>{errorMsg}</small>
      </div>
      <button class="button" on:click={handleClick}>Notify Me</button>
    </div>
  </section>
  <section class="img-container">
    <img
      class="dashboard-img"
      src="images/illustration-dashboard.png"
      alt="dashboard"
    />
  </section>
</main>

<footer class="footer">
  <ul class="icon-list">
    <li class="icon-list__item">
      <a class="icon" href="https://facebook.com" target="_blank"
        ><i class="fa-brands fa-facebook-f" /></a
      >
    </li>
    <li class="icon-list__item">
      <a class="icon" href="https://twitter.com" target="_blank"
        ><i class="fa-brands fa-twitter" /></a
      >
    </li>
    <li class="icon-list__item">
      <a class="icon" href="https://instagram.com" target="_blank"
        ><i class="fa-brands fa-instagram" /></a
      >
    </li>
  </ul>
  <small class="copyright">&copy; Copyright Ping. All rights reserved.</small>
</footer>

<style>
  .container {
    margin-top: 81px;
    margin-right: 27px;
    margin-left: 27px;
  }

  .primary-heading {
    font-size: 1.25rem;
    font-weight: 700;
    text-align: center;
    line-height: 1.01;
    color: var(--neutral-very-dark-blue);
  }
  .dot {
    color: var(--primary-blue);
  }

  .secondary-heading {
    margin-top: 32px;
    text-align: center;
    color: var(--neutral-gray);
    font-size: 1.375rem;
    font-weight: 300;
    line-height: 1.455;
  }

  .secondary-heading strong {
    color: var(--neutral-very-dark-blue);
    font-weight: 700;
  }

  .paragraph {
    color: var(--neutral-very-dark-blue);
    margin-top: 15px;
    text-align: center;
    font-weight: 300;
    font-size: 0.75rem;
    line-height: 1.21;
  }

  .interaction-group {
    margin-top: 32px;
    display: flex;
    flex-direction: column;
  }

  .input-group {
    width: 87.5%;
    margin-right: auto;
    margin-left: auto;
  }

  .email {
    width: 100%;
    padding-top: 10px;
    padding-bottom: 10px;
    padding-left: 32px;
    border: 1px solid var(--secondary-pale-blue);
    border-radius: 28px;
    box-shadow: 0px 0px 7px 3px hsla(0, 0%, 0%, 0);
    color: var(--secondary-pale-blue);
    font-weight: 300;
    font-size: 0.75rem;
    line-height: 1.67;
  }
  .email:focus {
    color: black;
  }

  .error {
    border: 1px solid var(--secondary-light-red);
  }

  .errorVisible {
    visibility: visible;
  }

  .error-msg {
    display: block;
    margin-top: 2px;
    text-align: center;
    color: var(--secondary-light-red);
    font-style: italic;
    font-size: 0.625rem;
    line-height: 2;
    letter-spacing: 0.13px;
  }

  .button {
    background-color: var(--primary-blue);
    /* box-shadow: 0px 5px 10px 2px hsla(223, 87%, 63%, 0.23); */
    box-shadow: 0px 5px 10px 2px rgba(76, 123, 243, 0.23);
    border-radius: 28px;
    border-style: none;
    margin-top: 20px;
    margin-right: auto;
    margin-left: auto;
    padding-top: 12px;
    padding-bottom: 12px;
    width: 87.5%;
    font-weight: 600;
    font-size: 0.75rem;
    line-height: 1;
    color: #fff;
  }

  .button:hover {
    /* background-color: hsla(223, 87%, 63%, 0.23); */
    background-color: var(--secondary-pale-blue);
    box-shadow: 0px 5px 10px 2px rgba(76, 123, 243, 0.23);
    transition: 0.05s ease-in;
  }

  .img-container {
    margin-top: 40px;
  }

  .dashboard-img {
    width: 100%;
  }

  .footer {
    margin-top: 120px;
    margin-bottom: 37px;
    width: 45.5%;
    margin-right: auto;
    margin-left: auto;
  }

  .icon-list {
    display: flex;
    list-style: none;
    justify-content: center;
  }
  .icon-list .icon-list__item:nth-child(2) {
    margin-right: 12px;
    margin-left: 12px;
  }

  .icon {
    display: block;
    color: var(--primary-blue);
    border: 1px solid hsla(223, 87%, 63%, 0.15);
    border-radius: 50%;
    padding: 0;
    line-height: 1.9em;
    width: 1.9em;
    text-align: center;
    /* width: 7px;
    height: 15px; */
  }

  .icon:hover {
    background-color: var(--primary-blue);
    color: #fff;
    transition: 0.2s ease-in-out;
  }

  .copyright {
    display: block;
    text-align: center;
    color: var(--neutral-gray);
    font-weight: 300;
    font-size: 0.625rem;
    line-height: 1.2;
    margin-top: 27px;
  }

  @media screen and (min-width: 1000px) {
    .container {
      width: 45%;
      max-width: 640px;
      margin-right: auto;
      margin-left: auto;
    }
    .primary-heading {
      font-size: 2rem;
      line-height: 1.22;
    }
    .secondary-heading {
      margin-top: 40px;
      font-size: 3rem;
      line-height: 1.25;
    }
    .paragraph {
      margin-top: 16px;
      font-size: 1.25rem;
    }
    .error-msg {
      font-size: 0.75rem;
      text-align: left;
      padding-left: 32px;
      margin-top: 6px;
    }
    .interaction-group {
      margin-top: 40px;
      display: flex;
      flex-direction: row;
    }
    .button {
      align-self: self-start;
      margin-top: 0;
      max-width: 200px;
    }
    .input-group {
      width: 65.7%;
      margin-right: 0;
      margin-left: 0;
    }
    .email {
      padding-top: 13px;
      padding-bottom: 13px;
      padding-left: 30px;
      font-size: 1rem;
    }
    .button {
      width: 31.2%;
      margin-right: 0px;
      padding-top: 18px;
      padding-bottom: 18px;
      /* padding-top: 16px;
      padding-bottom: 16px;
      padding-right: 62px;
      padding-left: 62px; */
      font-size: 1rem;
      line-height: 1.1875;
    }

    .footer {
      margin-top: 72px;
      margin-bottom: 49px;
      width: 14.2%;
      max-width: 204px;
      margin-right: auto;
      margin-left: auto;
    }

    /* .input-group {
      width: 65%;
      margin: 0;
    }
    .button {
      width: 31%;
      margin: 0;
    } */
  }
</style>
