<template>
    <section class="about">
        <h2>Who am I?</h2>
        <div class="container">


          <div class="card" v-on:mouseover="active = !active" v-on:mouseleave="active = !active">
            <div class="card--image">
              <img src="../assets/images/me-hi.jpeg" alt="Ken Taylor on a music video set" v-bind:style="{opacity: active ? 0.6 : 1 }">              
            </div>
            <div class="card--info info--1">
              <span class="info--text">WEB DEVELOPER</span>
              <div class="icon">
                <span class="expand">+</span>
              </div>
              <div class="info--image">
                <img src="../assets/images/webdev.png" alt="info image">
              </div>
            </div>
            <div class="card--info info--2">
              <span class="info--text">MUSICIAN</span>
              <div class="icon">
                <span class="expand">+</span>                
              </div>
              <div class="info--image">
                <img src="../assets/images/me2.jpg" alt="info image">
              </div>
            </div>
            <!-- <div class="card--info info--3">
              <span class="info--text">Dog Father</span>
              <div class="icon">
                <span class="expand">+</span>                
              </div>
              <div class="info--image">
                <img src="../assets/images/me2.jpg" alt="info image">
              </div>
            </div> -->
          </div>

        </div>
    </section>
</template>

<script>
export default {  
  data() {
    return {
      active: false
    }
  },

}
</script>

<style lang="scss">

.about {
  height: 100%;
  width: 100vh;  
  position: relative;
}

h2 {
  font-size: 9vw;
  width: 100%;
  position: absolute;
  opacity: 0.3;
  text-align: center;
  top: 11vh;
  z-index: 10;
}

.card {
	position: relative;
	width: 500px;
	height: 300px;
	box-shadow: 0 2.8px 2.2px rgba(0, 0, 0, 0.014), 0 6.7px 5.3px rgba(0, 0, 0, 0.02),
		0 12.5px 10px rgba(0, 0, 0, 0.025), 0 22.3px 17.9px rgba(0, 0, 0, 0.03),
		0 41.8px 33.4px rgba(0, 0, 0, 0.036), 0 100px 80px rgba(0, 0, 0, 0.05);
  background-color: black;

	&--image {
		width: 100%;
		height: 100%;
    position: relative;
		display: flex;
		justify-content: center;
		align-items: flex-end;
		overflow: hidden;
		img {
      position: absolute;
			width: 140%;
			height: 140%;
			object-fit: cover;
      transition: 0.3s ease-in-out;
      
		}
	}

	&--info {
		--size: 20px;
		width: var(--size);
		height: var(--size);
		background: rgba(0, 0, 0, 0.75);
		border-radius: 2px;
		position: absolute;
		transition: width 550ms ease, height 550ms ease, right 550ms ease, background 550ms ease;
		overflow: hidden;
		box-shadow: 0 2.8px 2.2px rgba(0, 0, 0, 0.014), 0 6.7px 5.3px rgba(0, 0, 0, 0.02),
			0 12.5px 10px rgba(0, 0, 0, 0.025), 0 22.3px 17.9px rgba(0, 0, 0, 0.03),
			0 41.8px 33.4px rgba(0, 0, 0, 0.036), 0 100px 80px rgba(0, 0, 0, 0.05),
			0 0px 2.2px rgba(0, 0, 0, 0.045), 0 0px 5.3px rgba(0, 0, 0, 0.065),
			0 0px 10px rgba(0, 0, 0, 0.08), 0 0px 17.9px rgba(0, 0, 0, 0.095),
			0 0px 33.4px rgba(0, 0, 0, 0.115), 0 0px 80px rgba(0, 0, 0, 0.16),
			0 0.2px 2.2px rgba(0, 0, 0, 0.014), 0 0.6px 5.3px rgba(0, 0, 0, 0.02),
			0 1.1px 10px rgba(0, 0, 0, 0.025), 0 2px 17.9px rgba(0, 0, 0, 0.03),
			0 3.8px 33.4px rgba(0, 0, 0, 0.036), 0 9px 80px rgba(0, 0, 0, 0.05);

		&::after {
			content: "";
			position: absolute;
			left: 0;
			top: 0;
			width: 100%;
			height: 100%;
			background: linear-gradient(
				to top,
				rgba(0, 0, 0, 0.65) 0%,
				rgba(0, 0, 0, 0.25) 50%,
				transparent 100%
			);
			z-index: 1;
			opacity: 0;
			transition: opacity 550ms ease;
		}

		&.info--1 {
			bottom: 47%;
			right: 80%;
			.info--image {
				img {
					top: 0%;
					left: 0%;
				}
			}
		}

		&.info--2 {
			bottom: 25%;
			right: 15%;
			.info--image {
				img {
					right: 0%;
					bottom: 0%;
				}
			}
		}

		.icon {
			position: absolute;
			width: 100%;
			height: 100%;
			top: 50%;
			left: 50%;
			transform: translate(-50%, -50%);
			display: flex;
			justify-content: center;
			align-items: center;
			.expand {
				color: rgba(255,255,255,0.4);
        font-size: 20px;
        position: relative;
        top: -1px;
			}
		}

		.info--text {
			display: block;
			position: absolute;
			left: 10%;
			bottom: 5%;
			font-size: 0.88rem;
			letter-spacing: 1px;
			// font-family: "Montserrat";
			font-weight: bold;
			color: #fff;
			white-space: nowrap;
			z-index: 2;
			opacity: 0;
			transform: translateY(25%);
			transition: opacity 250ms ease, transform 250ms ease;
		}

		.info--image {
			position: relative;
			width: 100%;
			height: 100%;
			overflow: hidden;
			img {
				position: absolute;
				width: 100%;
				height: 100%;
				object-fit: cover;
				opacity: 0;
				transition: opacity 550ms ease;
			}
		}
	}

	&:hover {
		.card--info {
			--size: 250px;
			&::after {
				opacity: 1;
			}
			&.info--1 {
				right: 81%;
				transition-delay: 100ms;
			}
			&.info--2 {
				right: -30%;
        bottom: 20%;
			}
			.info--image {
				img {
					opacity: 1;
				}
			}
			.info--text {
				transition-delay: 550ms;
				opacity: 1;
				transform: translateY(0%);
			}
		}
	}
}

</style>