<template>
  <div class="container">
    <div class="extended-header"></div>

    <div class="contact-container">
      <div class="outter-shell">
        <div class="image-holder">
          <img src="~/static/images/contact.png" alt="">
        </div>

        <div class="contacts-holder">
          <div class="contacts">
            <h3>Contact us!</h3>

            <p class="contact-text">Dui vivamus arcu felis bibendum. Diam quam nulla porttitor massa id neque.</p>

            <div class="addresses">
              <div class="email">
                <i class="fas fa-envelope"></i>
                <span>plateium@email.com</span>
              </div>

              <div class="phone">
                <i class="fas fa-phone"></i>
                <span>+123 234 2344</span>
              </div>
            </div>
          </div>

          <div class="message-container">
            <h3>Message us</h3>

            <div class="email-inputs">
              <plt-input placeholder="Email" class="email-input" title="Your email address"/>
              <plt-input placeholder="Title" title="Title of message"/>
            </div>

            <div class="text-area">
              <plt-input placeholder="message" tag="textarea" title="Message"/>
            </div>

            <div class="button-container">
              <plt-button>Send message</plt-button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
    }
  },
}
</script>

<style lang="scss" scoped>
.extended-header {
  background: $primary-color;
  height: 370px;
}
.contact-container {
  display: flex;
  align-items: center;
  flex-direction: column;
  margin-top: -290px;
}
.outter-shell {
  display: flex;
  align-items: center;
}
.image-holder {
  width: 375px;
  height: 430px;
  box-shadow: $box-shadow;
  z-index: 1;
  overflow: hidden;
  border-radius: $radius-default;

  img {
    object-fit: cover;
    object-position: center;
    width: 100%;
    height: 100%;
  }
}
.contacts-holder {
  width: 600px;
  margin-left: -$space-l;
  z-index: 2;
}
.contacts, .message-container {
  box-shadow: $box-shadow;
  border-radius: $radius-default;
  background: #fff;
  padding: $space-s $space-m;
}
.contacts {
  margin-bottom: 32px;
}
.contact-text {
  margin: $space-m 0;
  color: $font-color-lighter;
}
.addresses, .phone, .email {
  display: flex;

  span {
    color: $font-color-light;
  }
  i {
    font-size: 22px;
    color: $font-color-lighter;
    margin-right: $space-xs;
  }
}
.email {
  margin-right: $space-l;
}
.message-container {
}
.email-inputs {
  display: flex;
  justify-content: space-between;
  margin-bottom: $space-s;
}
.email-input {
  margin-right: $space-m;
}
.button-container {
  display: flex;
  justify-content: flex-end;
  margin-top: $space-m;
}
</style>
