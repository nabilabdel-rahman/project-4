# UOCIS322 - Project 4 #

Author: Nabil Abdel-Rahman

Contact: nabilabdel-rahman@outlook.com

This project consists of a web application that is based on RUSA's online calculator. The algorithm for calculating controle times is described here https://rusa.org/pages/acp-brevet-control-times-calculator. Additional background information is given here https://rusa.org/pages/rulesForRiders. The description is ambiguous, but the examples help. Part of finishing this project is clarifying anything that is not clear about the requirements, and documenting it clearly.

We are essentially replacing the calculator here https://rusa.org/octime_acp.html. We can also use that calculator to clarify requirements and develop test data.

We run the calculator using Docker and Flask to load the page onto our machine locally. In a Linux environment, use the command "docker build -t some-image-name ." to build the image for the page and then use the command "docker run -d -p 5001:5000 some-image-name". A Dockerfile is provided in the folder "brevets" in order to run the program. Make sure to adjust the Dockerfile accordingly to your local machine's needs and requirements. Further, all page templates are provided in the folder "templates". Lastly, a skeleton to create your credentials page to run the program is provided as well. If not created, the program will use the default.ini to run the program.

The frontend, calc.html, contains a javascript which allows for AJAX requests to the flask application. The file acp_times.py computes the calculations and returns it back to the flask application, which processes the data and returns the date and time for each interval back to calc.html, which then updates the page accordingly.

A file called test_acp_times.py is provided to hold test cases to ensure that the calculations in acp_times.py are correct. Some tests contains variables which can be manipulated to ensure different scenarios are correct. To run the tests, in your terminal, make sure your current directory is "brevets" and run the command "nosetests tests/test_acp_times.py".

Make sure to run the commands docker stop and to delete the container and image when finished running the program.