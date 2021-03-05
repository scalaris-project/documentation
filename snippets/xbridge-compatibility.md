<style>
.md-typeset__scrollwrap {
	overflow-x: visible;
}
.md-typeset .md-typeset__table #bn-table {
		margin-bottom: -15px;
}
</style>

<!-- 
<form>
	Asset Lookup: <input id="sb_input" type="text" placeholder="Enter asset"/>
	<br><br>
</form>
-->

!!! warning "**DO NOT** use a wallet version not listed here, it is either not compatible or hasn't been tested."

???+ abstract "Compatible with Blocknet wallet v1.0.x"
	[View Manifest](https://github.com/scalaris-project/blockchain-configuration-files/blob/master/manifest-latest.json)

	<table id="bn-table">
		<thead>
			<tr>
				<th>Digital Asset</th>
				<th>Ticker</th>
				<th>Supported Wallet Versions</th>
			</tr>
		</thead>
		<tbody id="bn-tbody">
		</tbody>
	</table>




<script type="text/javascript">
var manifestURL = "https://raw.githubusercontent.com/scalaris-project/blockchain-configuration-files/master/manifest-latest.json";
// var manifestURL = "https://raw.githubusercontent.com/scalaris-project/blockchain-configuration-files/1.0.0.0/manifests/manifest-1.0.0.0.json";
var dumpTable = false;

getManifest().then(tabulate);
function getManifest() {
	var manifestPromise = new Promise(function(resolve, reject){
		ajax(manifestURL, true).then(function(manifest) {
			manifestJSON = manifest;
			localStorage.setItem('manifest', JSON.stringify(manifest));
			resolve(manifestJSON);
		}, false);
	});
	return manifestPromise;
}
function ajax(url, json) {
	var ajaxPromise = new Promise(function(resolve, reject){
		var xhr = new XMLHttpRequest();
		var status = true;
		xhr.open('GET', url);
		xhr.send();
		xhr.onreadystatechange = function(){
			if (xhr.readyState === 4 && xhr.status === 200){
				var response = json ? JSON.parse(this.responseText) : this.responseText
				resolve(response);
			}
		}
	});
	return ajaxPromise;
}
function tabulate(data) {
	var manifest = data;
	var preTable = {};
	var table = "";
	var nameLength = 0;
	var tickerLength = 0;
	// max lengths based off the markdown header character column widths
	var maxNameLength = 16;
	var maxTickerLength = 7;

	for(var asset in manifest) {
		var name = manifest[asset]["blockchain"];
		var ticker = manifest[asset]["ticker"];
		var nameSpaces = 0;
		var tickerSpaces = 0;
		if (dumpTable) {
			nameSpaces = (name.length < maxNameLength) ? (maxNameLength - name.length) : 0;
			name += (nameSpaces == 1)  ? " " : 
							(nameSpaces == 2)  ? "  " : 
							(nameSpaces == 3)  ? "   " : 
							(nameSpaces == 4)  ? "    " : 
							(nameSpaces == 5)  ? "     " : 
							(nameSpaces == 6)  ? "      " :
							(nameSpaces == 7)  ? "       " :
							(nameSpaces == 8)  ? "        " :
							(nameSpaces == 9)  ? "         " :
							(nameSpaces == 10) ? "          " :
							(nameSpaces == 11) ? "           " :
							(nameSpaces == 12) ? "            " :
							(nameSpaces == 13) ? "             " :
							(nameSpaces == 14) ? "              " :
							(nameSpaces == 15) ? "               " :
							" ";
			tickerSpaces = (ticker.length < maxTickerLength) ? (maxTickerLength - ticker.length) : 0;
			if (nameSpaces == 0) { tickerSpaces = 0 }
			ticker += (tickerSpaces == 1)  ? " " : 
								(tickerSpaces == 2)  ? "  " : 
								(tickerSpaces == 3)  ? "   " : 
								(tickerSpaces == 4)  ? "    " : 
								(tickerSpaces == 5)  ? "     " : 
								(tickerSpaces == 6)  ? "      " : 
								" ";
		}

		var repo = manifest[asset]["repo_url"];
		if (repo.substr(-1) === "/") {
			repo = repo.slice(0, -1);
		}
		repo += "/releases/tag/";

		var versionsArray = manifest[asset]["versions"];
		var versionLinks = "";
		for (var version in versionsArray) {
			var versionLink;
			if (dumpTable) {
				// output markdown linked version text
				versionLink = '[' + versionsArray[version] + '](' + repo + versionsArray[version] + ')';
			} else {
				// output html linked version text <a href="repo url">version</a>
				versionLink = '<a href="' + repo + versionsArray[version] + '">' + versionsArray[version] + '</a>';
			}
			// if only 1 version
			if (versionsArray.length < 2) {
				versionLinks += versionLink;
			} else {
				// if last version in array (no comma)
				if (version == versionsArray.length - 1) {
					versionLinks += versionLink;
				// if not the last version (add comma)
				} else {
					versionLinks += versionLink + ", ";
				}
			}
		}

		// if multiple version groups of same blockchain then combine versionLinks (e.g. btc v15-v18)
		if (preTable[name]) {
			preTable[name]["versions"] += ", " + versionLinks;
		} else {
			preTable[name] = {"name": name, "ticker": ticker, "versions": versionLinks};
		}
	}

	for (var asset in preTable) {
		var row;
		if (dumpTable) {
			// use for older deprecated versions
			// row = preTable[asset]["name"] + "|" + preTable[asset]["ticker"] + "|" + preTable[asset]["versions"];
			// use for newest version
			row = "<tr><td>" + preTable[asset]["name"] + "</td><td>" + preTable[asset]["ticker"] + "</td><td>" + preTable[asset]["versions"] + "</td><tr>";
			table += row + "\n";
		} else {
			row = "<tr><td>" + preTable[asset]["name"] + "</td><td>" + preTable[asset]["ticker"] + "</td><td>" + preTable[asset]["versions"] + "</td><tr>";
			table += row;
		}
	}
	if (dumpTable) {
		console.log(table);
	} else {
		document.getElementById("bn-tbody").innerHTML = table;
	}
}


</script>