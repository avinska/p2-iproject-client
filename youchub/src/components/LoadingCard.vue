<script>
export default {
  name: "LoadingCard",
};
</script>

<template>
  <div class="card col-md-3 border-0 mb-3 mt-0" style="max-width: 18rem">
    <div class="shimmerBG thumbnail"></div>
    <div></div>
    <div class="card-body row">
      <div class="ms-3 col-2">
        <div class="shimmerBG avatar"></div>
      </div>
      <div class="col-9">
        <div class="shimmerBG title-line mt-0"></div>
        <div class="shimmerBG title-line three-fifth"></div>
        <div class="shimmerBG content-line two-fifth"></div>
        <div class="shimmerBG content-line three-quarter"></div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.card {
  padding: 10px;
}
.card-body {
  padding: 4px;
}
.col-10,
.col-2 {
  padding: 0;
}

.thumbnail,
.avatar,
.title-line,
.content-line {
  background: #ddd;
  width: 100%;
  border-radius: 20px;
  margin: 8px 0px;
}
.thumbnail {
  height: 120px;
  border-radius: 8px;
}
.avatar {
  height: 42px;
}
.title-line {
  height: 16px;
}
.content-line {
  height: 12px;
}
.three-fifth {
  width: 60%;
}
.three-quarter {
  width: 75%;
}
.two-fifth {
  width: 40%;
}

.shimmerBG {
  animation-duration: 2.2s;
  animation-fill-mode: forwards;
  animation-iteration-count: infinite;
  animation-name: shimmer;
  animation-timing-function: linear;
  background: #ddd;
  background: linear-gradient(to right, #f6f6f6 8%, #f0f0f0 18%, #f6f6f6 33%);
  background-size: 1200px 100%;
}

@-webkit-keyframes shimmer {
  0% {
    background-position: -100% 0;
  }
  100% {
    background-position: 100% 0;
  }
}

@keyframes shimmer {
  0% {
    background-position: -1200px 0;
  }
  100% {
    background-position: 1200px 0;
  }
}

.media {
  height: 200px;
}
</style>
