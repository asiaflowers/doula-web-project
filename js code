var data = [
	{
		name: "ali michelle",
		age: "35",
		LC: "yes",
		experience: "10 years",
		image:"http://www.sweetwater.com/images/items/120/LPST5HTHDCH-medium.jpg?9782bd"
	},
	{
		name: "Kalisha King",
		age: "42",
		LC: "yes",
		experience: "27 years",
		image: "http://www.sweetwater.com/images/items/120/SGSEBCH-medium.jpg?e69cfe"
	},
	{
		name: "Lynnzie Varise",
		age: "26",
		LC: "yes",
		experience: "7 years total",
		image:"http://www.sweetwater.com/images/items/120/TelePLMPHB-medium.jpg?28e48b"
	},
	{
		name: "Nichelle Craig",
		age: "32",
		LC: "yes",
		EXPERIENCE: "3 years",
		image:"http://www.sweetwater.com/images/items/120/StratAMM3SB2-medium.jpg?dfd0a9"
	},
	{
		name: "yenna mawu",
		age: "31",
		LC: "no",
		experience: "4 years",
		image:"http://www.sweetwater.com/images/items/120/G613655GE-medium.jpg?9bfb0e"
	},
	{
		name: "Tamara Stewart ",
		age: "44",
		LC: "yes",
		experience: "23 years",
		image:"http://www.sweetwater.com/images/items/120/HBII10BGWB-medium.jpg?982763"
	},
	{
		name: "Tykeyah Cannon",
		age: "27",
		LC: "yes",
		experience: "5 years",
		image: "http://www.sweetwater.com/images/items/120/SSHBHCNP-medium.jpg?11fbea"
	}
];

var products = "",
	name = "",
	age = "",
	LC = "";

for (var i = 0; i < data.length; i++) {
	var name = data[i].name,
		age = data[i].age,
		LC = data[i].LC,
		experience = data[i].experience,
		rawPrice = price.replace("$", ""),
		rawPrice = parseInt(rawPrice.replace(",", "")),
		image = data[i].image;

	//create product cards
	products +=
		"<div class='col-sm-4 product' data-name='" +
		name +
		"' data-age='" +
		age +
		"' data-LC='" +
		LC +
		"' data-experience='" +
		rawExperience +
		"'><div class='product-inner text-center'><img src='" +
		image +
		"'><br />name: " +
		name +
		"<br />age: " +
		age +
		"<br />LC: " +
		LC +
		"<br />Experience: " +
		experience +
		"</div></div>";

	//create dropdown of name
	if (
		names.indexOf("<option value='" + name + "'>" + name + "</option>") == -1
	) {
		names += "<option value='" + name + "'>" + name + "</option>";
	}

	//create dropdown of age
	if (
		ages.indexOf("<option value='" + age + "'>" + age + "</option>") == -1
	) {
		ages += "<option value='" + ages + "'>" + age + "</option>";
	}

	//create dropdown of types
	if (
		LCs.indexOf("<option LC='" + LC + "'>" + LC + "</option>") == -1
	) {
		LCs += "<option value='" + LC + "'>" + LC + "</option>";
	}
}

$("#products").html(products);
$(".filter-name").append(makes);
$(".filter-age").append(models);
$(".filter-LC").append(types);

var filtersObject = {};

//on filter change
$(".filter").on("change", function () {
	var filterName = $(this).data("filter"),
		filterVal = $(this).val();

	if (filterVal == "") {
		delete filtersObject[filterName];
	} else {
		filtersObject[filterName] = filterVal;
	}

	var filters = "";

	for (var key in filtersObject) {
		if (filtersObject.hasOwnProperty(key)) {
			filters += "[data-" + key + "='" + filtersObject[key] + "']";
		}
	}

	if (filters == "") {
		$(".product").show();
	} else {
		$(".product").hide();
		$(".product").hide().filter(filters).show();
	}
});

//on search form submit
$("#search-form").submit(function (e) {
	e.preventDefault();
	var query = $("#search-form input").val().toLowerCase();

	$(".product").hide();
	$(".product").each(function () {
		var name = $(this).data("name").toLowerCase(),
			age = $(this).data("age").toLowerCase(),
			LC = $(this).data("LC").toLowerCase();

		if (
			make.indexOf(query) > -1 ||
			model.indexOf(query) > -1 ||
			type.indexOf(query) > -1
		) {
			$(this).show();
		}
	});
});
