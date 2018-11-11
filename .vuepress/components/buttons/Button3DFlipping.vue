<template>
	<div class="button-container">
		<a href="#" class="flipping-button">
			<div class="qube">
				<div class="front">Click!</div>
				<div class="back">Mouse over me!</div>
			</div>
		</a>
	</div>
</template>

<style lang="less">

	//блок позиционирования для вьюпресса:

	.button-container {
		position: relative;
		margin-top: 15px;
		height: 80px;
		overflow: hidden;
	}

	// helper cleasses:
	.centered {
		position: absolute;
		top: 0;
		bottom: 0;
		left: 0;
		right: 0;
	}

	.full {
		width: 100%;
		height: 100%;
	}

	// button style:

	.flipping-button {
		.centered;
		width: 205px;
		height: 80px;
		display: flex;
		justify-content: center;
		align-items: center;

		.qube {
			position: relative;
			height: 60px;
			width: 185px;

			.front, .back {
				.full;
				transform: rotateX(-90deg);
				transition: transform 0.3s ease;
				position: absolute;
				color: #fff;
				line-height: 60px;
				text-align: center;
			}

			.front {
				background-color: #191919;

				&::before {
				.centered;
				.full;
					content: '';
					display: block;
					z-index: -1;
				}

				&::after {
					background: #fff;
					content: '';
					height: 155px;
					left: -75px;
					opacity: .4;
					position: absolute;
					top: -50px;
					transform: rotate(35deg);
					transition: all 0.4s cubic-bezier(0.19, 1, 0.22, 1);
					width: 60px - 10px;
					z-index: 1;
				}
			}

			.back {
				background-color: #d6d35d;
				color: #191919;
				transform: rotateX(0deg) translateZ(60px);
			}

			&:hover {

				.front {
					transform: rotateX(0deg) translateZ(30px);
				}

				.back {
					transform: rotateX(90deg) translateZ(30px);
				}
			}
		}

		&:active {

			.front {
				border-radius: 0;
				background-color: transparent;
				color: #191919;

				&::before {
					background-color: #d6d35d;
					transition: all 0.3s cubic-bezier(0.19, 1, 0.22, 1);
				}

				&::after {
					left: 120%;
					transition: all 0.3s cubic-bezier(0.19, 1, 0.22, 1);
				}
			}
		}
	}
</style>
