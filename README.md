# THINGS IN HERE

## GEMS

```
gem "sassc-rails"
gem 'simple_form'
gem 'devise'
gem 'bootstrap-sass'
```
- sassc for scss
- didnt use bootstrap
- devise set for turbo, rails 7
- from: https://dev.to/efocoder/how-to-use-devise-with-turbo-in-rails-7-9n9

### jQuery raty
- had 2 different ones per show page
- added the images to assets/images
- adding jquery via cdns

```
    <script src="https://code.jquery.com/jquery-3.6.1.min.js" integrity="sha256-o88AwQnZB+VDvE9tvIXrMQaPlFFSUTR+nldQm1LuPXQ=" crossorigin="anonymous"></script>    
    <script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/raty/2.9.0/jquery.raty.js"></script>
```
- added to the show page
```
<script>
	$('.review-rating').raty({
		readOnly: true,
		score: function() {
			return $(this).attr('data-score');
		},
		path: '/assets/'
	});
</script>

<script>
	$('.average-review-rating').raty({
		readOnly: true,
		path: '/assets/',
		score: function() {
			return $(this).attr('data-score')
		}
	});
</script>
```

## MODELS
- devise user
- user has many plays and reviews
- plays has images, belongs to user and categories, has many reviews
- reviews belongs to users and plays
- categories has many plays

## OTHER
- used custom stylings
- imported fonts via the app.scss

```
@import url(https://fonts.googleapis.com/css?family=Lato); 
```

- showed the categories if they are in the params

```
<h1 class="current-category"><%= params[:category] %></h1>
```

- filter plays based on categories