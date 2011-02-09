# jQuery Google Analytics Plugin

# Usage

Here is an example of `$.track` used to track page load speeds:

	<!-- After opening head tag -->
	<script>
		pageLoadStart = new Date();
	</script>
	
	...
	
	<!-- Just before the closing body tag -->
	<script>
		$(function(){
			pageLoadEnd = new Date();
			
			$.track(
				'_trackEvent',
				'Page Load',
				'Loaded',
				document.location.pathname + (document.location.search ? document.location.search : ''),
				((pageLoadEnd.getTime() - pageLoadStart.getTime()) / 1000).toFixed(3)
			);
		});
	</script>
