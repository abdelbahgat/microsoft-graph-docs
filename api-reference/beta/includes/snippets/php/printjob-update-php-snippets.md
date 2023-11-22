---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new PrintJob();
$configuration = new PrintJobConfiguration();
$configuration->setFeedOrientation(new PrinterFeedOrientation('longEdgeFirst'));
$pageRangesIntegerRange1 = new IntegerRange();
$pageRangesIntegerRange1->setStart(1);
$pageRangesIntegerRange1->setEnd(1);
$pageRangesArray []= $pageRangesIntegerRange1;
$configuration->setPageRanges($pageRangesArray);

$configuration->setQuality(new PrintQuality('medium'));
$configuration->setDpi(600);
$configuration->setOrientation(new PrintOrientation('landscape'));
$configuration->setCopies(1);
$configuration->setDuplexMode(new PrintDuplexMode('oneSided'));
$configuration->setColorMode(new PrintColorMode('blackAndWhite'));
$configuration->setInputBin('by-pass-tray');
$configuration->setOutputBin('output-tray');
$configuration->setMediaSize('A4');
$configurationMargin = new PrintMargin();
$configurationMargin->setTop(0);
$configurationMargin->setBottom(0);
$configurationMargin->setLeft(0);
$configurationMargin->setRight(0);
$configuration->setMargin($configurationMargin);
$configuration->setMediaType('stationery');
$configuration->setFinishings(null);
$configuration->setPagesPerSheet(1);
$configuration->setMultipageLayout(new PrintMultipageLayout('clockwiseFromBottomLeft'));
$configuration->setCollate(false);
$configuration->setScaling(new PrintScaling('shrinkToFit'));
$configuration->setFitPdfToPage(false);
$requestBody->setConfiguration($configuration);

$result = $graphServiceClient->escapedPrint()->printers()->byPrinterId('printer-id')->jobs()->byPrintJobId('printJob-id')->patch($requestBody)->wait();

```