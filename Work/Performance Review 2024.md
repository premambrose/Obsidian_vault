# [Technical Research on AI](https://fa-ewua-saasfaprod1.fa.ocs.oraclecloud.com/hcmUI/faces/FuseWelcome?_adf.ctrl-state=hrqscxmv8_1&_adf.no-new-window-redirect=true&_afrLoop=26132766560833399&_afrWindowMode=2&_afrWindowId=null&_afrFS=16&_afrMT=screen&_afrMFW=2552&_afrMFH=1282&_afrMFDW=2560&_afrMFDH=1440&_afrMFC=8&_afrMFCI=0&_afrMFM=0&_afrMFR=96&_afrMFG=0&_afrMFS=0&_afrMFO=0#)

1. Prepare a patent proposal on the objective "Door knock application" by Q4 
2. Develop a port from H7 to N6 of an AI application by Q4 
3. Study of SOTA on drowsiness and level of attention monitoring and preparation of a feasibility report (Q4)

Self Assessment
1. Patent Proposal for Door Knock Detection
    - A detailed patent proposal for the Door Knock Detection application has been prepared and is awaiting submission. This AI application is designed to enhance security and convenience by detecting and responding to door knocks using ISPU sensor. The system can differentiate between Knocks and trigger appropriate responses, such as sending notifications or activating security cameras.
2. Porting AI Application from H7 to N6
    - The replication of an example program on the STM32N6570-DK board, utilizing a camera, has been successfully executed. However, I encountered issues with the installation of the STEdgeAI core on the company laptop due to proxy restrictions. This toolchain is essential for converting AI models to run on the N6 platform. I am actively working with the IT department to resolve this issue. The transition involves adapting existing AI models to the new hardware specifications, with the STM32N6570-DK board serving as the testbed.
3. Study of State-of-the-Art (SOTA) on Drowsiness and Attention Level Monitoring
    - An extensive study of State-of-the-Art (SOTA) techniques in drowsiness and attention level monitoring has been completed. The findings have been compiled into a feasibility report and presented to the internal subgroup focused on attention monitoring. The study reviews the latest research, technologies, and methodologies, evaluating various approaches such as machine learning algorithms and real-time monitoring systems to enhance user safety and performance.

# [Maze Game 3.0](https://fa-ewua-saasfaprod1.fa.ocs.oraclecloud.com/hcmUI/faces/FuseWelcome?_adf.ctrl-state=hrqscxmv8_1&_adf.no-new-window-redirect=true&_afrLoop=26132766560833399&_afrWindowMode=2&_afrWindowId=null&_afrFS=16&_afrMT=screen&_afrMFW=2552&_afrMFH=1282&_afrMFDW=2560&_afrMFDH=1440&_afrMFC=8&_afrMFCI=0&_afrMFM=0&_afrMFR=96&_afrMFG=0&_afrMFS=0&_afrMFO=0#)

1. Development of Motor Control System to Stabilize Ball in Position
    - A sophisticated motor control system based on Proportional-Integral-Derivative (PID) control has been meticulously integrated into the application. This system effectively stabilizes the ball's position on a plane without walls by utilizing a camera to capture the coordinates in real-time. Additionally, a smooth control algorithm was layered on top of the PID control, which considers the previous 'n' positions of the ball to create a smooth error curve, thereby minimizing jerks and ensuring fluid motion of the ball on the plane. The placement of the two motors was optimized by relocating them from the front to each side of the plane's axis, with one motor dedicated to controlling the pitch and the other to managing the roll. This configuration enhances the system's responsiveness and stability, providing precise control over the ball's position.
2. Development of Dynamic Wall Detection and Gameplay Re-routing Application
    - An advanced real-time remapping system for the maze was developed, leveraging camera and image processing technologies to dynamically understand and adapt to the maze map. This system is capable of handling any 19x13 dimension map and is programmed to solve games with dynamic walls. The AI was developed to manage up to six dynamic walls (or blocks) within the map, ensuring seamless gameplay adjustments in real-time. This capability allows the application to detect changes in the maze environment and re-route the gameplay accordingly, providing a robust and adaptive gaming experience.
3. Development of Multi-step Inference for Smooth Gameplay
    - A one-shot gameplay system was created to optimize the pathfinding process. This system calculates the full path to the game's end upon the ball's initial drop by mapping the ball's position in a matrix and sending it to the AI thread. The AI then simulates the entire game in a virtual matrix, returning the complete path to the goal. The motor control system then smoothly guides the ball along this path, ensuring a fluid and uninterrupted gaming experience. This one-shot pathfinding process takes less than one second, even for the longest paths, significantly reducing the need for continuous frame-by-frame inference. If external disturbances or dynamic wall changes occur, the one-shot gameplay recalculates the path, demonstrating the system's resilience and adaptability.
4. Feasibility Analysis of Gameplay Without Walls
    - The wall-less gameplay was rigorously tested on a paper-drawn maze map placed on an acrylic plate connected to two motors. This setup was demonstrated to the internal team led by Viviana, showcasing the system's capabilities. In Q4, the acrylic plate was replaced with a lightweight LCD monitor mounted on the two motors. The STM32MP157D-DK1 board was upgraded to the STM32MP25bF-EV1 for improved performance, as the former had become obsolete. The LCD panel, controlled by the MP2 board, displayed the maze map and other graphics (ball position, next move, goal, virtually reconstructed map, etc.). The application begins with an initialization mode, where the MP1 draws four blue blocks at each corner of the maze map. These blocks are used to define the region of interest for further image processing. Once detected, the system transitions to actual gameplay. These corner blocks help transform and recreate the map and accurately position the ball, even if the plane is not perfectly aligned with the camera. The ball is then placed on the LCD panel, which serves as the new gameplay region, providing a visually engaging and technically advanced gaming experience.

# [Development of a system for the monitoring of drowsiness and level of attention](https://fa-ewua-saasfaprod1.fa.ocs.oraclecloud.com/hcmUI/faces/FuseWelcome?_adf.ctrl-state=hrqscxmv8_1&_adf.no-new-window-redirect=true&_afrLoop=26132766560833399&_afrWindowMode=2&_afrWindowId=null&_afrFS=16&_afrMT=screen&_afrMFW=2552&_afrMFH=1282&_afrMFDW=2560&_afrMFDH=1440&_afrMFC=8&_afrMFCI=0&_afrMFM=0&_afrMFR=96&_afrMFG=0&_afrMFS=0&_afrMFO=0#)

1) Participate to the activity of the dedicated working group(Q4) 
2) Explore and collect public datasets (Q4) 
3) Define a plan for a POC to be realized next year (Q4)

Self Assessment
1. Participation in the Dedicated Working Group (Q4)
    - - I have been actively participating in the working group focused on attention monitoring. My contributions have been instrumental in advancing the group's objectives. I have supported the group by sharing insights, engaging in discussions, and presenting a comprehensive presentation on the topic of Driver Drowsiness Detection Systems. This presentation covered various aspects, including the latest technologies, methodologies, and their practical applications in real-world scenarios. Additionally, I created few sample datasets of images and videos using technologies such as the Stable Diffusion Model, ControlNet Technology, and the OpenPose Model. These datasets were generated through text-to-image and video-to-video pipelines and consist of photorealistic faces of individuals from diverse ethnicities, genders, and age groups, captured in various face rotation positions. My active involvement has fostered collaboration and knowledge sharing within the group, driving progress toward our collective goals.
2. Exploration and Collection of Public Datasets (Q4)
    - An extensive study of the State-of-the-Art (SOTA) in driver drowsiness detection systems has been conducted. This study involved exploring and summarizing the datasets used in these SOTA works. By analyzing these datasets, I have identified key patterns, trends, and gaps in the existing data, which will inform future research and development efforts. The findings from this study were presented to the working group, providing valuable insights and laying the groundwork for the collection of relevant public datasets. This initiative aims to enhance the robustness and accuracy of our drowsiness detection models.
3. Defining a Plan for a Proof of Concept (POC) to be Realized Next Year (Q4)
    -   Currently, we are engaged in active discussions to finalize the specifics of this plan, ensuring comprehensive alignment. This is crucial for refining the plan and addressing potential challenges, paving the way for a seamless and successful implementation in 2025.
# [Engaged People - Collaborating](https://fa-ewua-saasfaprod1.fa.ocs.oraclecloud.com/hcmUI/faces/FuseWelcome?_adf.ctrl-state=hrqscxmv8_1&_adf.no-new-window-redirect=true&_afrLoop=26133531925391680&_afrFS=16&_afrMT=screen&_afrMFW=1270&_afrMFH=1274&_afrMFDW=2560&_afrMFDH=1440&_afrMFC=8&_afrMFCI=0&_afrMFM=0&_afrMFR=96&_afrMFG=0&_afrMFS=0&_afrMFO=1#)

1. Increase the level of collaboration with colleagues.

Self Assessment
1. Increase the Level of Collaboration with Colleagues
   - This year, I have significantly enhanced my collaboration with colleagues by actively participating in a working group focused on attention monitoring. I engaged with two team members, incorporating their feedback to refine our methodologies and improve outcomes. Additionally, I collaborated with my manager and experts in C application development, which helped me optimize performance and accelerate development timelines. This collaborative approach has not only improved my technical skills but also fostered a more cohesive and productive working environment.

# [Bold Leadership - Communicating with Conviction](https://fa-ewua-saasfaprod1.fa.ocs.oraclecloud.com/hcmUI/faces/FuseWelcome?_adf.ctrl-state=hrqscxmv8_1&_adf.no-new-window-redirect=true&_afrLoop=26133531925391680&_afrFS=16&_afrMT=screen&_afrMFW=1270&_afrMFH=1274&_afrMFDW=2560&_afrMFDH=1440&_afrMFC=8&_afrMFCI=0&_afrMFM=0&_afrMFR=96&_afrMFG=0&_afrMFS=0&_afrMFO=1#)

1. Complete A1 Italian Course before Q4 with a certification from the GoFluent or any other platform. 
2. Prepare a technical presentation on the Maze game/Door Knock (or both) application in Italian.

Self Assessment
1. Complete A1 Italian Course before Q4 with Certification
    - I have been dedicated to learning Italian by using the book "Italian in 3 Months." To confirm my progress, I took the exam on the GoFluent platform and successfully passed the A2 level, surpassing my initial A1 goal. This accomplishment is supported by the attached certification.
2. Prepare a Technical Presentation on the Maze Game/Door Knock Application in Italian
    - In the December internal meeting, I presented my work on the maze game application in Italian. The presentation covered the development process, technical challenges, and solutions. 

# [Smart Thinking - Developing Expertise](https://fa-ewua-saasfaprod1.fa.ocs.oraclecloud.com/hcmUI/faces/FuseWelcome?_adf.ctrl-state=hrqscxmv8_1&_adf.no-new-window-redirect=true&_afrLoop=26133531925391680&_afrFS=16&_afrMT=screen&_afrMFW=1270&_afrMFH=1274&_afrMFDW=2560&_afrMFDH=1440&_afrMFC=8&_afrMFCI=0&_afrMFM=0&_afrMFR=96&_afrMFG=0&_afrMFS=0&_afrMFO=1#)

1. Complete two technical courses from online platforms like LinkedIn learn, Coursera, etc. One before June and one before December. 
2. Read and summarize three books or articles related to my area of expertise one each Quarter year.

Self Assessment
1. Complete Two Technical Courses from Online Platforms
    - I successfully completed four courses on Coursera. These courses include:
        1. Custom Models, Layers, and Loss Functions with TensorFlow: This course provided in-depth knowledge on creating custom models and layers, enhancing my understanding of machine learning frameworks.
        2. Custom and Distributed Training with TensorFlow: This course focused on advanced training techniques, including distributed training, which is essential for scaling machine learning models.
        3. Generative AI: Prompt Engineering by IBM: This course introduced me to the fundamentals of generative AI and prompt engineering, broadening my expertise in AI technologies.
        4. Docker Essentials and Building a Containerized Web Application: This course covered the basics of Docker and how to build and deploy containerized applications, improving my skills in DevOps and application deployment.
2. Read and Summarize Three Books or Articles Related to My Area of Expertise
    - I read and summarized the following key articles:
        1. Quantum in Progress: Strategies from Revolution to Industry Event: This article provided insights into the latest advancements and strategies in quantum computing, highlighting its transition from theoretical research to practical industry applications.
        2. Humanoid Robotics Development and Technical Insights: This article explored the development of humanoid robots, discussing technical challenges, innovations, and future directions in robotics.

# Stake holder
- Simone
- Davide
- Roberto
- Danilo
- Alberto villa
- Davide ALIPRANDI