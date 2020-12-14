<!DOCTYPE html>

<head>
    <!-- Latest compiled and minified CSS -->
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u"
        crossorigin="anonymous">

    <!-- Optional theme -->
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap-theme.min.css" integrity="sha384-rHyoN1iRsVXV4nD0JutlnGaslCJuC7uwjduW9SVrLvRYooPp2bWYgmgJQIXwl/Sp"
        crossorigin="anonymous">

    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/azsearch.js@0.0.21/dist/AzSearch.css">
    <title>AzSearch.js</title>
    <style>
        .searchResults__result h4 {
            margin-top: 0px;
            text-transform: uppercase;
        }

        .searchResults__result .resultDescription {
            margin: 0.5em 0 0 0;
        }
    </style>
</head>

<body>
    <div id="app">
        <nav class="navbar navbar-inverse navbar-fixed-top">
            <div class="container-fluid">
                <div class="navbar-header">
                    <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#facetPanel" aria-expanded="false"
                        aria-controls="navbar">
                        <span class="sr-only">Toggle navigation</span>
                        <span class="icon-bar"></span>
                        <span class="icon-bar"></span>
                        <span class="icon-bar"></span>
                    </button>
                    <div class="row">
                        <div class="col-md-2 pagelabel">
                            <a class="navbar-brand pagelabel" href="https://github.com/Azure-Samples/AzSearch.js">AzSearch.js</a>
                        </div>
                        <div id="searchBox" class="col-mid-8 col-sm-8 col-xs-6"></div>
                        <div id="navbar" class="navbar-collapse collapse">

                        </div>
                    </div>
                </div>
            </div>
        </nav>

        <div class="container-fluid">
            <div class="row">
                <div id="facetPanel" class="col-sm-3 col-md-3 sidebar collapse">
                    <div id="clearFilters"></div>
                    <ul class="nav nav-sidebar">
                        <div className="panel panel-primary behclick-panel">
                            
                            <li>
                                <div id="content/Request/FormulaNameFacet">
                                </div>
                            </li>
                            <li>
                                <div id="content/Request/ProductTypeCodeFacet">
                                </div>
                            </li>
                            <li>
                                <div id="SubmissionSucceededFacet">
                                </div>
                            </li>
                            <li>
                                <div id="content/ErrorFacet">
                                </div>
                            </li>
                            <li>
                                <div id="content/Request/UserNameFacet">
                                </div>
                            </li>
                            <li>
                                <div id="content/Response/MessageFacet">
                                </div>
                            </li>
                            <li>
                                <div id="content/Request/TargetPanel/PanelNameFacet">
                                </div>
                            </li>
                            <li>
                                <div id="content/Request/ReleasePanel/PanelNameFacet">
                                </div>
                            </li>
                            <li>
                                <div id="content/Request/TargetPanel/GlossFacet">
                                </div>
                            </li>
                            <li>
                                <div id="content/Request/ReleasePanel/GlossFacet">
                                </div>
                            </li>
                            <li>
                                <div id="content/Request/TargetPanel/MeasurementData/DeviceModelInfo/MeasurementSchemeFacet">
                                </div>
                            </li>
                            <li>
                                <div id="content/Request/ReleasePanel/MeasurementData/DeviceModelInfo/MeasurementSchemeFacet">
                                </div>
                            </li>
                            <li>
                                <div id="content/Request/ColorNameFacet">
                                </div>
                            </li>
                            <li>
                                <div id="content/Request/Ingredients/MasterRexFacet">
                                </div>
                            </li>
                            <li>
                                <div id="content/Request/ParentFormulaIdFacet">
                                </div>
                            </li>
                            <li>
                                <div id="content/Request/ParentFormulaNumberFacet">
                                </div>
                            </li>
                        </div>
                    </ul>
                </div>
                <div class="col-sm-9 col-sm-offset-3 col-md-9 col-md-offset-3 results_section">
                    <div id="results" class="row placeholders">
                    </div>
                    <div id="pager" class="row">
                    </div>
                </div>
            </div>
        </div>
        <!-- Bootstrap core JavaScript
            ================================================== -->
        <!-- Placed at the end of the document so the pages load faster -->
        <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.12.4/jquery.min.js"></script>
        <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js" integrity="sha384-Tc5IQib027qvyjSMfHjOMaLkfuWVxZxUPnCJA7l2mCWNIpG9mGCD8wGNIcPD7Txa"
            crossorigin="anonymous"></script>
</body>
<!-- Dependencies -->
<script src="https://cdn.jsdelivr.net/react/15.5.0/react.min.js"></script>
<script src="https://cdn.jsdelivr.net/react/15.5.0/react-dom.min.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/redux/3.6.0/redux.min.js"></script>
<!-- Main -->
<script src="https://cdn.jsdelivr.net/npm/azsearch.js@0.0.21/dist/AzSearch.bundle.js"></script>
<script>
    // Initialize and connect to your search service
    var automagic = new AzSearch.Automagic({ index: "dev-fsi-index", queryKey: "A48A3552B9548E7CE6E1EB0DA333AD42", service: "mosaic-fsi-search" });
    // add a results view using the template defined above
    automagic.addResults("results", { count: true });
    // Adds a pager control << 1 2 3 ... >>
    automagic.addPager("pager");
    
        automagic.addSearchBox("searchBox");
        
       automagic.addCheckboxFacet("content/Request/FormulaNameFacet", "content/Request/FormulaName", "string");
   automagic.addCheckboxFacet("content/Request/ProductTypeCodeFacet", "content/Request/ProductTypeCode", "string");
   automagic.addCheckboxFacet("SubmissionSucceededFacet", "SubmissionSucceeded", "string");
   automagic.addCheckboxFacet("content/ErrorFacet", "content/Error", "string");
   automagic.addCheckboxFacet("content/Request/UserNameFacet", "content/Request/UserName", "string");
   automagic.addCheckboxFacet("content/Response/MessageFacet", "content/Response/Message", "string");
   automagic.addCheckboxFacet("content/Request/TargetPanel/PanelNameFacet", "content/Request/TargetPanel/PanelName", "string");
   automagic.addCheckboxFacet("content/Request/ReleasePanel/PanelNameFacet", "content/Request/ReleasePanel/PanelName", "string");
   automagic.addCheckboxFacet("content/Request/TargetPanel/GlossFacet", "content/Request/TargetPanel/Gloss", "number");
   automagic.addCheckboxFacet("content/Request/ReleasePanel/GlossFacet", "content/Request/ReleasePanel/Gloss", "number");
   automagic.addCheckboxFacet("content/Request/TargetPanel/MeasurementData/DeviceModelInfo/MeasurementSchemeFacet", "content/Request/TargetPanel/MeasurementData/DeviceModelInfo/MeasurementScheme", "string");
   automagic.addCheckboxFacet("content/Request/ReleasePanel/MeasurementData/DeviceModelInfo/MeasurementSchemeFacet", "content/Request/ReleasePanel/MeasurementData/DeviceModelInfo/MeasurementScheme", "string");
   automagic.addCheckboxFacet("content/Request/ColorNameFacet", "content/Request/ColorName", "string");
   automagic.addCheckboxFacet("content/Request/Ingredients/MasterRexFacet", "content/Request/Ingredients/MasterRex", "string");
   automagic.addCheckboxFacet("content/Request/ParentFormulaIdFacet", "content/Request/ParentFormulaId", "string");
   automagic.addCheckboxFacet("content/Request/ParentFormulaNumberFacet", "content/Request/ParentFormulaNumber", "string");


    // Adds a button to clear any applied filters
    automagic.addClearFiltersButton("clearFilters");
</script>
<style>

</style>

</html>
