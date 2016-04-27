# Objective
The default LESS mixins that handle the Bootstrap grid aren't as compact as I would like. It takes four lines to specify standard breakpoint behaviour and passing a value of 0 does not result in hidden columns for that breakpoint. I decided to make this to simplify my own development life; feel free to use it for your own person interests and to build upon it.

# Compilation Instructions
1. Download the Bootstrap LESS theme, be it through Node or some other means
2. Include `mixins.less` to your LESS compile path
3. Compile and use

# Usage Examples

Standard Bootstrap LESS:

	.my-column {
		.make-xs-column(12);
		.make-sm-column(12);
		.make-md-column(6);
		.make-lg-column(4);
	}

	.my-other-column {
		.hidden-xs;
		.hidden-sm;
		.hiddem-md;
		.make-lg-column(12);
	}

With this mixin file:

	.my-column {
		.make-column(12,12,6,4);
	}

	.my-other-column {
		.make-column(0,0,0,12);
	}

Additionally, media queries are provided to very easily target individual breakpoints. Mobile (xs,sm) and desktop (md,lg) queries are also available. They can be used as such:

	.using-media-query {
		display: none;

		@media @xs-only {
			display: block;
		}
	}

	.using-media-query-2 {
		font-size: 12px;

		@media @mobile {
			font-size: 16px;
		}
	}

File originally written by Muhammad Abdul-Rahim.