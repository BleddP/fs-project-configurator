<template>
  <div>
    <div class="flex-wrapper padding">
      <div class="container-center">
        <div class="row">
          <div class="col-4">
            <p class="question">Heb je een vraag?</p>
            <h2>Een oplossing voor u vinden?</h2>
            <p class="light-gray-text">
              Stel je vraag aan onze sales specialist. We helpen je graag
              verder.
            </p>
            <div class="row padding-25">
              <div class="col-3 contact-intro">
                <p>Direct Contact</p>
                <h3 class="orange-text">
                  info@alpha-deuren.nl
                </h3>
              </div>
              <div class="col-3 contact-intro">
                <p>Telefonisch Contact</p>
                <h3 class="orange-text">
                  +31 31 687 798
                </h3>
              </div>
            </div>
          </div>
          <div class="col-2">
            <div class="flex-center-all">
              <img
                src="https://images.unsplash.com/photo-1591786409812-8260a746fd1c?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=917&q=80"
                alt="Helpdesk"
                class="image"
              />
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="orange-strip"></div>
  </div>
</template>

<script>
export default {
  name: 'ConfigContact',
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.padding {
  padding-top: 100px;
  z-index: 10;
}

.padding-25 {
  padding-top: 50px;
}

.orange-strip {
  height: 250px;
  background: rgb(255, 166, 0, 0.2);
  transform: translateY(-200px);
  z-index: 5;
}

.question {
  color: orange;
  font-weight: bold;
}

.contact-intro {
  color: gray;
  font-weight: bold;
}

.image {
  border-radius: 5px;
  width: 500px;
  height: 400px;
  z-index: 10;
}
</style>
