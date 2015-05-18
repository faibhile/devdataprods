# devdataprods project


An attempt to amend the lecture code to calculate the length of the hypotenuse given the lengths of the adjacent and opposite.


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
        headerPanel("Hello Shiny!"),
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
                p('Output text3'),
                textOutput('text3')
        )
))

```
