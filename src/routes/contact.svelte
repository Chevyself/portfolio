<script>
  import Navbar from "../components/Navbar.svelte";
  import { onMount } from "svelte";

  // Add a class to the input if the content is invalid
  function validateInput(input) {
    if (input.validity.valid || input.value === "") {
      input.classList.remove("invalid");
    } else {
      input.classList.add("invalid");
    }
  }

  // onMount get all the inputs type email
  onMount(() => {
    const inputs = document.querySelectorAll("input[type=email]");
    inputs.forEach((input) => {
      input.addEventListener("input", () => {
        validateInput(input);
      });
    });
    // When the group is clicked the input or textare is focused
    const groups = document.querySelectorAll(".group");
    groups.forEach((group) => {
      group.addEventListener("click", () => {
        const input = group.querySelector("input");
        const textarea = group.querySelector("textarea");
        if (input) {
          input.focus();
        } else if (textarea) {
          textarea.focus();
        }
      });
    });
    // Increase textarea height when the content is bigger
    const textareas = document.querySelectorAll("textarea");
    textareas.forEach((textarea) => {
      textarea.addEventListener("input", () => {
        textarea.style.height = "auto";
        textarea.style.height = textarea.scrollHeight + "px"; 
        // Change the height of #main accordingly to the height of the textarea
        const main = document.querySelector("#main");
        main.style.height = "auto";
        main.style.height = (main.scrollHeight > window.innerHeight ? (main.scrollHeight + (window.innerHeight * 0.5)) : main.scrollHeight) + "px";
    });
  });
  });
</script>

<header>
  <Navbar />
</header>

<section id="main" class="container-fluid d-flex flex-column">
  <div>
    <h2>
      Feel free to email me to <a href="mailto:chevyself@gmail.com"
        >chevyself@gmail.com</a
      >
    </h2>
    <p class="fs-4">You can also use this contact form:</p>
  </div>
  <div class="dflex justify-content-center container-xxl">
    <form
      action="https://docs.google.com/forms/u/0/d/e/1FAIpQLSc0i3LXBxWVVPQQUBP7ZdAZMVN1alJIPr2bZLT0JsMTnYcLvg/formResponse"
      method="POST"
      id="mG61Hd"
    >
      <div class="group">
        <input type="text" name="entry.1939435893" required />
        <label for="entry.1939435893" class="form-label">Name</label>
        <div class="bar" />
      </div>
      <div class="group">
        <input id="email" type="email" name="entry.308462723" required />
        <label for="entry.308462723" class="form-label">Email</label>
        <div class="bar" />
      </div>
      <div class="group">
        <textarea name="entry.1442677703" rows="1" required />
        <label for="entry.1442677703" class="form-label">Message</label>
        <div class="bar" />
      </div>
      <div class="d-flex justify-content-center text-light mt-3">
        <button type="submit" class="btn btn-outline-primary btn-lg"
          ><i class="bi bi-fast-forward" /></button
        >
      </div>
    </form>
  </div>
</section>

<style lang="scss">
  @import "../styles/variables.scss";
  @import "../../node_modules/bootstrap/scss/functions";
  @import "../../node_modules/bootstrap/scss/variables";

  #main {
    min-height: 100vh;
    height: auto;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  // Make button animation smooth
  button {
    transition: 0.3s ease;
  }

  // Input styles

  // Variables
  $font-size: $h3-font-size;
  $font-size-small: calc($font-size / 2);
  $label-font-size: calc($font-size * 0.8);
  $label-font-size-small: calc($font-size-small * 0.8);

  // Each input group
  .group {
    width: 100%;
    height: auto;
    font-size: $font-size;
    overflow: hidden;
    position: relative;
  }

  // Label initial style (Makes it look like a placeholder)
  label {
    position: absolute;
    top: calc($font-size * 1);
    color: $gray-500;
    cursor: text;
    transition: 0.25s ease;
    @media (max-width: 991.98px) {
      top: calc($font-size-small * 1);
    }
  }

  // Dont allow textarea to be resized
  textarea {
    resize: none;
  }

  // Input and textarea initial styles
  input,
  textarea {
    display: block;
    width: 100%;
    padding-top: calc($font-size * 1.5);
    border: none;
    border-radius: 0; // For iOS
    color: $white;
    background: transparent;
    transition: 0.3s ease;

    @media screen and (max-width: 991.98px) {
      padding-top: calc($font-size-small * 1.5);
    }

    // Style when input is valid
    &:valid {
      ~ label {
        top: 0;
        color: $primary;
        font-size: $label-font-size;
      }

      ~ .bar:before {
        transform: translateX(0);
      }
    }

    // Style when input is focused
    &:focus {
      outline: none;
      ~ label {
        top: 0;
        color: $primary;
        font-size: $label-font-size;
      }

      ~ .bar:before {
        transform: translateX(0);
      }
    }

    // Stop Chrome's hideous pale yellow background on auto-fill
    &:-webkit-autofill {
      -webkit-box-shadow: 0 0 0px 1000px $primary inset;
      -webkit-text-fill-color: white !important;
    }
  }

  // The bar idle
  .bar {
    background: $gray-500;
    content: "";
    width: 100%;
    height: calc($font-size * 0.1);
    transition: 0.1s ease;
    position: relative;
    &:before {
      content: "";
      position: absolute;
      width: 100%;
      height: 100%;
      background: $primary;
      transform: translateX(-100%);
    }
  }

  // Invalid on input hack
  input:global(.invalid) {
    // border-bottom-color: $main-color;
    ~ label {
      top: 0;
      color: $danger;
      font-size: $label-font-size;
    }

    ~ .bar:before {
      background: $danger;
    }
    // Apply the style to every input pseudo class
    &:checked,
    &:disabled,
    &:enabled,
    &:focus,
    &:in-range,
    &:invalid,
    &:optional,
    &:out-of-range,
    &:read-only,
    &:read-write,
    &:required,
    &:valid {
      ~ label {
        top: 0;
        color: $danger;
        font-size: $label-font-size;
      }

      ~ .bar:before {
        transform: translateX(0);
      }
    }
  }
</style>
