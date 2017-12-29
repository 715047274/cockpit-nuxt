<template>
  <div class="card">
    <div class="card-image">
      <div class="grid">


      <figure class="effect-roxy">
        <img v-bind:src="post.ImageUrl" />

        <figcaption>
							<h2 class="title is-4">
                    {{ post.Title }}
              </h2>
							<p></p>

              <nuxt-link  :to="{ name: 'detail', params: { postContent: post.Content, postTitle: post.Title}}">View more</nuxt-link>
				</figcaption>
      </figure>
    </div>
    </div>
<!--

    <div class="card-footer">
    </div> -->
  </div>
</template>

<style>
.effect-roxy{
  background:linear-gradient(45deg, #ff89e9 0%,#05abe0 100%);

}
.grid{
  position: relative;
margin: 0 auto;
padding: 0 0 4em;
max-width: 1000px;
list-style: none;
text-align: center;
}
.grid figure{
  position: relative;
float: left;
overflow: hidden;
margin: 0;
max-height: 360px;
width: 100%;
background: #3085a3;
text-align: center;
cursor: pointer;
}
.effect-roxy img{
    position: relative;
    display: block;
    max-width: 100%;
    opacity: 0.8;
    max-width: none;
    width: -webkit-calc(100% + 60px);
    width: calc(100% + 60px);
    -webkit-transition: opacity 0.35s, -webkit-transform 0.35s;
    transition: opacity 0.35s, transform 0.35s;
    -webkit-transform: translate3d(-50px,0,0);
    transform: translate3d(-50px,0,0);
}
.effect-roxy figcaption::before{
  position: absolute;
  top: 30px;
  right: 30px;
  bottom: 30px;
  left: 30px;
  border: 1px solid #fff;
  content: '';
  opacity: 0;
  -webkit-transition: opacity 0.35s, -webkit-transform 0.35s;
  transition: opacity 0.35s, transform 0.35s;
  -webkit-transform: translate3d(-20px,0,0);
  transform: translate3d(-20px,0,0);
}
.effect-roxy h2{
  padding: 30% 0 10px 0;
  margin:0;
}
.effect-roxy p{
  opacity: 0;
  -webkit-transition: opacity 0.35s, -webkit-transform 0.35s;
  transition: opacity 0.35s, transform 0.35s;
  -webkit-transform: translate3d(-10px,0,0);
  transform: translate3d(-10px,0,0);
}
figcaption > a{
  z-index: 1000;
  text-indent: 200%;
  white-space: nowrap;
  font-size: 0;
  opacity: 0;

  position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
}
  .card-image{
    text-align: center;
    padding: 0;
    color: white;
  }
  .card{
    height: 100%;
    display: flex;
    flex-direction: column;
  }
  .title{
    color:white;
  }
  .card-footer{
    margin-top: auto;
  }
  figcaption{
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }


  figure.effect-roxy {
  	background: -webkit-linear-gradient(45deg, #ff89e9 0%, #05abe0 100%);
  	background: linear-gradient(45deg, #ff89e9 0%,#05abe0 100%);

  }

  figure.effect-roxy img {
  	max-width: none;
  	width: -webkit-calc(100% + 60px);
  	width: calc(100% + 60px);
  	-webkit-transition: opacity 0.35s, -webkit-transform 0.35s;
  	transition: opacity 0.35s, transform 0.35s;
  	-webkit-transform: translate3d(-50px,0,0);
  	transform: translate3d(-50px,0,0);
    filter: brightness(60%);

  }

  figure.effect-roxy figcaption::before {
  	position: absolute;
  	top: 30px;
  	right: 30px;
  	bottom: 30px;
  	left: 30px;
  	border: 1px solid #fff;
  	content: '';
  	opacity: 0;
  	-webkit-transition: opacity 0.35s, -webkit-transform 0.35s;
  	transition: opacity 0.35s, transform 0.35s;
  	-webkit-transform: translate3d(-20px,0,0);
  	transform: translate3d(-20px,0,0);
  }

  figure.effect-roxy figcaption {
  	padding: 3em;
  	text-align: left;
  }

  figure.effect-roxy h2 {
  	padding: 30% 0 10px 0;
  }

  figure.effect-roxy p {
  	opacity: 0;
  	-webkit-transition: opacity 0.35s, -webkit-transform 0.35s;
  	transition: opacity 0.35s, transform 0.35s;
  	-webkit-transform: translate3d(-10px,0,0);
  	transform: translate3d(-10px,0,0);
  }

  figure.effect-roxy:hover img {
  	opacity: 0.7;
  	-webkit-transform: translate3d(0,0,0);
  	transform: translate3d(0,0,0);
    filter: brightness(85%);
  }

  figure.effect-roxy:hover figcaption::before,
  figure.effect-roxy:hover p {
  	opacity: 1;
  	-webkit-transform: translate3d(0,0,0);
  	transform: translate3d(0,0,0);
  }

  .column{
    min-width: 250px;
  }

</style>

<script>

export default {
  props: {
    post: {
      type: Object,
      required: true
    }
  }
}
</script>
