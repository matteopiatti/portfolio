<script>
	import * as j from 'jquery';
	import { onMount } from 'svelte';

	onMount(() => {
		j(document).ready(function(){
			j('.this-is-the-scroll-element').scroll(function() {
				console.log('lol')
				positionCar();			
			});

			// init the line car position
			positionCar();

			function positionCar() {
				var  scrollY = j('.this-is-the-scroll-element').scrollTop() || window.pageYOffset;
				var  maxScrollY = j('.this-is-the-scroll-element').prop('scrollHeight');
				var  path = document.getElementById("path");
				// Calculate distance along the path the car should be for the current scroll amount
				var  pathLen = path.getTotalLength();
				var  dist = pathLen * scrollY / maxScrollY;
				var  pos = path.getPointAtLength(dist);
				// Calculate position a little ahead of the car (or behind if we are at the end), so we can calculate car angle
				if (dist + 1 <= pathLen) {
					var  posAhead = path.getPointAtLength(dist + 1);
					var angle = Math.atan2(posAhead.y - pos.y, posAhead.x - pos.x);

				} else {
					var  posBehind = path.getPointAtLength(dist - 1);
					var angle = Math.atan2(pos.y - posBehind.y, pos.x - posBehind.x);
				}
				// Position the car at "pos" totated by "angle" (if angle is upwards position further for more speed)
				var  car = document.getElementById("c");
				car.setAttribute("transform", "translate(" + (pos.x) + "," + (pos.y) + ") rotate(" + (rad2deg(angle) + 90) + ")");
			}

			function rad2deg(rad) {
				return 180 * rad / Math.PI;
			}

		});
});
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<div style="position:absolute; top:0; right:0; left:0; z-index:1000; pointer-events: none;" id="route">
	<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 966 4692" id="svgRoute">
		<path id="path" d="M652 0V239.5V317.5C538.333 325.5 312.9 402.4 320.5 646C328.1 889.6 474.667 970.5 547 980.5C573.667 983 632 988.7 652 991.5C677 995 806 993 798 1118.5C791.6 1218.9 628 1275.67 547 1291.5C372.5 1294.67 30.1999 1323.2 56.9999 1412C90.4999 1523 171.5 1565.5 293.5 1607C415.5 1648.5 707 1657 786.5 1931C850.1 2150.2 436.667 2111 222 2064C64.5001 2047.5 -163.9 2094.8 182.5 2416C528.9 2737.2 800.5 2670.5 893 2597C984.5 2452 1061.5 2189 637.5 2297C213.5 2405 390.167 2773.67 531.5 2944.5C665.833 3062 924 3334.1 882 3482.5C829.5 3668 442 3885.5 420 3990C398 4094.5 764.5 4537 774 4691" stroke-width="5"  stroke="none" fill="none"/>
		<image id="c" x="-20" y="-70" width="40" height="70" xlink:href="data:img/png;base64,iVBORw0KGgoAAAANSUhEUgAAAF4AAACqCAYAAAAk0fhhAAAFP0lEQVR4nO2dzWtcZRSH36tjGKdNOkOSFpqk+RAtqVGEtGahWLQQF0JMKBhQqKjVnVu7dK3gqiC4qGDAhQtpCC4kEOgsKooWQWuDYD9i81EH25RGrUlTx3/gnIvvzXWeKfk9y9+de8+dh7M4vPcrqdfrodlIkiTPk0qskP7f96HVtzESDyHxEBIPIfEQEg+RkGOVNzaOjR/LrcbM9JRb3tvQCCfqeAiJh5B4CImHkHiIQiOKxE4vn53+JLfakxN2PjM95Y4uSZL87wtr6ngIiYeQeAiJh5B4iFzXavKaXqpnvndrPLKv1cx79naa+WZxl5lPTrzq1ohd38niUB0PIfEQEg8h8RASDyHxENHjZNpdXnmNjW++9pZb/4Xxl8z8nbft1TBvzCwUS26NFyeOm3meY6Y6HkLiISQeQuIhJB4i10t/vV3tZp5levFY/u2Gmb9/8rSZe9NO/0CvW8P7H3mijoeQeAiJh5B4CImHaMgNTR4rK9fMfOixx6OP5U07zYo6HkLiISQeQuIhJB4CnWo8zv/4g7tt38PxE08zoo6HkHgIiYeQeAiJh5B4iIaMk+X2DjP/4suZ6GN598ffvLZs5qWW5uyt5jyrbYDEQ0g8hMRDSDxEQ6aa7p4uM+/YvcfMdxY23WO1ljbMvFqzb7su3vnHzO3KjUMdDyHxEBIPIfEQEg+BXvq7urBg5qWif1qd5fvN/OLyX2Y+tKsl/sQagDoeQuIhJB5C4iEkHiLXqWZ17U6ehzO5e/ummb/7rH1laj0pmvmvi7+7NRrxP9TxEBIPIfEQEg8h8RASD+GOk1m+t7ejtbK1s9kCV2prZj7QZ5/TqQ/tdx+EEMJPv9Riy5uuvNehh6COx5B4CImHkHgIiYeIXiTr6Xva3bZnb/+WTua/0NkR9/akv9ftG6CycGTUfq/m3Kz7PkoXdTyExENIPITEQ0g8RMFbkxl+cszcoVa7t96ElCdjky9H/X5u1v+snToeQuIhJB5C4iEkHiJ6raa1Yj9Ith3o7rK/N5IFdTyExENIPITEQ0g8hMRDoE/9tZXtm42KD6Ts05ayMScOHhox86WV67nVUMdDSDyExENIPITEQ7hTTblcNvNHB/zXiJ+tnonKb7Vwt3W3baxG7/PUc8/nVl8dDyHxEBIPIfEQEg8RvVazdMn/cEr17Ndm3ldfMvPjz9hvf2wZtCeqEEJ4sP8hM799+aKZb8zb7z746Cv/XQa3KvvNfMfUSXefWNTxEBIPIfEQEg8h8RDuI9/BeUw8C68fHDTzU684O4ymPMR2YMDOL1yy89nLZvzGp36Jj7+b9zdGcGT0mB6pbzYkHkLiISQeQuIhJB7CXSRLG4U80p5yi2F1wf6gSgghVA7E7ZPnxcX2nkOmkycG7XE5DXU8hMRDSDyExENIPEShXrcHkZRXJqKsXbAv5TWC61e/NfM5J09DHQ8h8RASDyHxEBIP4a7VeNNOGt4kdONP+zNxIdyNrrG54N+IFIN/TvFkcaWOh5B4CImHkHgIiYdAH6n/5vPdZj5y1P7AbgghrO7vNfPKz/Y+Xo0Q8ns8PgvqeAiJh5B4CImHkHgIiYdIsizwuAfzLxeaRQ53D5s/fq9vp1tj5Kj9OThvbDxx5Q8zry6ec2uMDw6Zf2R6/rz5ey2S3UNIPITEQ0g8hMRDNGSRzJ8SzpnjwIlgTzshhBA+KDkb4qaXw93DKXdsrfubckIdDyHxEBIPIfEQEg+R61qNW8RZw/HWaqqL9rSThfTpxcabhPJ0pY6HkHgIiYeQeAiJh5B4iH8BrZ8Mhx0ulsYAAAAASUVORK5CYII="/>
	</svg>  
</div>

<style>
#route {
  margin-top: 400px;
}

svg {
	width:74%;
	height:auto;
}
</style>