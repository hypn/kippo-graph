Package: Kippo-Graph
Version: 0.7
Author: ikoniaris
Website: bruteforce.gr/kippo-graph

Kippo-Graph is a full featured script to visualize statistics from a Kippo SSH honeypot.

It uses "Libchart" PHP chart drawing library by Jean-Marc Trémeaux,
"QGoogleVisualizationAPI" PHP Wrapper for Google's Visualization API by Thomas Schäfer
and geoPlugin geolocation technology (geoplugin.com)

REQUIREMENTS:
You need to have “php5-gd” and “php5-mysql” packages installed. On Ubuntu/Debian:
apt-get update && apt-get install -y php5-gd php5-mysql
/etc/init.d/apache2 restart

QUICK INSTALLATION:
wget http://bruteforce.gr/wp-content/uploads/kippo-graph-VERSION.tar
mv kippo-graph-VERSION.tar /var/www
cd /var/www
tar xvf kippo-graph-VERSION.tar --no-same-permissions
cd kippo-graph
chmod 777 generated-graphs
vi config.php #enter the appropriate values

Browse to http://your-server/kippo-graph to generate the statistics.

Note 1: If you are on a VPS/server and don't want to use the default Apache document root, 
		you will still need to add a new Apache vhost and enable the site.
Note 2: To fully use the geolocation features (Intensity Map) you will need to give CREATE 
		TEMPORARY TABLES rights to your Kippo database user (most likely it has already been done).
Note 3: Kippo-Geo component displays a warning pop-up after rendering the Google Map.
		You can either ignore it because it doesn't really affect the functionality or remove it by
		generating a Google Maps API key (version 2) per the link instructions and putting it in
		kippo-graph/include/qgooglevisualapi/QApikeyGoogleGraph.class.php, in the form of:
		const KEY = “http://maps.google.com/maps?file=api&v=2&key=XXXXXXXXXXXXXXXXXXXXXXXX”;
		(make sure to remove the '{' and '}')
