---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphprint "github.com/microsoftgraph/msgraph-beta-sdk-go/print"
	  graphmodels "github.com/microsoftgraph/msgraph-beta-sdk-go/models"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphprint.NewRedirectPostRequestBody()
destinationPrinterId := "9a3b3956-ce5b-4d06-a605-5b0bd3e9ddea"
requestBody.SetDestinationPrinterId(&destinationPrinterId) 
configuration := graphmodels.NewPrintJobConfiguration()
feedOrientation := graphmodels.LONGEDGEFIRST_PRINTERFEEDORIENTATION 
configuration.SetFeedOrientation(&feedOrientation) 


integerRange := graphmodels.NewIntegerRange()
start := int64(1)
integerRange.SetStart(&start) 
end := int64(1)
integerRange.SetEnd(&end) 

pageRanges := []graphmodels.IntegerRangeable {
	integerRange,
}
configuration.SetPageRanges(pageRanges)
quality := graphmodels.MEDIUM_PRINTQUALITY 
configuration.SetQuality(&quality) 
dpi := int32(600)
configuration.SetDpi(&dpi) 
orientation := graphmodels.LANDSCAPE_PRINTORIENTATION 
configuration.SetOrientation(&orientation) 
copies := int32(1)
configuration.SetCopies(&copies) 
duplexMode := graphmodels.ONESIDED_PRINTDUPLEXMODE 
configuration.SetDuplexMode(&duplexMode) 
colorMode := graphmodels.BLACKANDWHITE_PRINTCOLORMODE 
configuration.SetColorMode(&colorMode) 
inputBin := "by-pass-tray"
configuration.SetInputBin(&inputBin) 
outputBin := "output-tray"
configuration.SetOutputBin(&outputBin) 
mediaSize := "A4"
configuration.SetMediaSize(&mediaSize) 
margin := graphmodels.NewPrintMargin()
top := int32(0)
margin.SetTop(&top) 
bottom := int32(0)
margin.SetBottom(&bottom) 
left := int32(0)
margin.SetLeft(&left) 
right := int32(0)
margin.SetRight(&right) 
configuration.SetMargin(margin)
mediaType := "stationery"
configuration.SetMediaType(&mediaType) 
finishings := null
configuration.SetFinishings(&finishings) 
pagesPerSheet := int32(1)
configuration.SetPagesPerSheet(&pagesPerSheet) 
multipageLayout := graphmodels.CLOCKWISEFROMBOTTOMLEFT_PRINTMULTIPAGELAYOUT 
configuration.SetMultipageLayout(&multipageLayout) 
collate := false
configuration.SetCollate(&collate) 
scaling := graphmodels.SHRINKTOFIT_PRINTSCALING 
configuration.SetScaling(&scaling) 
fitPdfToPage := false
configuration.SetFitPdfToPage(&fitPdfToPage) 
requestBody.SetConfiguration(configuration)

redirect, err := graphClient.Print().Printers().ByPrinterId("printer-id").Jobs().ByPrintJobId("printJob-id").Redirect().Post(context.Background(), requestBody, nil)


```