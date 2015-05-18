# devdataprods project





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
