# devdataprods project


An attempt to amend the lecture code to calculate the length of the hypotenuse (of a right angled triangle) given the lengths of the adjacent and opposite.
Hypotenuse = (Adjacent^2 + Opposite^2)^0.5 


```{r}
shinyServer(
        function(input, output) {
                output$Adjacent <- renderText({input$Adjacent})
                output$Opposite <- renderText({input$Opposite})
                output$text3 <- renderText({
                        input$goButton
                        isolate(paste(input$Adjacent, input$Opposite))
                })
        }
)
````






```{r}
shinyUI(pageWithSidebar(
        headerPanel("Shiny triangle!"),
        sidebarPanel(
                textInput(inputId="Adjacent", label = "Length Adjacent"),
                textInput(inputId="Opposite", label = "Length Opposite"),
                actionButton("goButton", "Go!")
        ),
        mainPanel(
                p('Output Adjacent'),
                textOutput('Adjacent'),
                p('Output Opposite'),
                textOutput('Opposite'),
                p('Output Hypotenuse'),
                textOutput('Hypotenuse')
        )
))


```
