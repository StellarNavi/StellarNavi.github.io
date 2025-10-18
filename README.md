  Hello 👋 I’m Audrey Weaver, and I am completing my Bachelor of Science in Computer Science with a concentration in Data Analytics. Over the course of this program, I have developed both the technical depth and professional confidence to design, build, troubleshoot, and deliver impactful software solutions. This ePortfolio, which features my custom capstone project<a href="https://www.mymessiertracker.com/" target="_blank" rel="noopener noreferrer">My Messier Tracker</a>, serves as proof of my skills to apply computer science principles to solve meaningful problems through full-stack development, database engineering, and data visualization as well as my drive for continuous learning as is required in this field.
  Throughout my projects, I have learned to think like both an engineer and an analyst. Early courses in algorithms and data structures built my foundation in logical problem solving and computational efficiency. I have strengthened my skills in software engineering and database design by learning to create secure, modular, and well-documented systems. My concentration in data analytics, through my professional work and this project, shows my ability to extract actionable insights from complex data and meaningfully communicate those findings clearly to technical and non-technical stakeholders alike. These experiences have shaped my professional values around precision, transparency, and a user-focused design.
  The My Messier Tracker project is a culmination of those skills. It is a full-stack web application that allows users to track, document, and analyze their astrophotography progress across the Messier catalog. The project integrates a PostgreSQL database, Flask back end, and interactive front end featuring real user data and visualizations. Through this process, I demonstrated software engineering discipline, database optimization, user authentication and security design, and the ability to transform raw data into meaningful insights as well as the ability to troubleshoot issues, pivot and enhance a product which are all essential skills for both software and data-focused roles.
  Collaboration and communication have been central to my success in this program and in my professional work. I’ve collaborated in agile-style environments, managed code versions through Git and GitHub, and practiced clear documentation through proper documentation and comments as well as participated in peer reviews. I’ve also communicated technical details to diverse audiences, from project stakeholders to non-technical teammates, ensuring shared understanding of both system design and data interpretation. These experiences have prepared me to thrive in dynamic, cross-functional teams.
  Security has also been an integral part of my mindset in every project. In My Messier Tracker, I implemented secure authentication practices, hashed passwords, and database safeguards to prevent injection attacks. This attention to security reflects my commitment to developing software that not only performs well but also protects user privacy and data integrity.
  My ePortfolio showcases three major enhancements representing core areas of computer science: software engineering, algorithms and data structures, and databases. Together, these artifacts demonstrate a comprehensive range of technical and analytical skills such as designing efficient algorithms, building scalable databases, implementing robust CRUD operations, integrating data visualizations, and maintaining secure architectures. Collectively, these enhancements reflect my ability to turn well designed ideas into a production-ready applications that deliver value to users.
  As I enter the next stage of my career, I bring a passion for data-driven problem solving, a strong foundation in software development, database structure and analytics as well as a continual drive to learn and build meaningful solutions. This program has equipped me not only with technical competence but also with a mindset of curiosity, discipline, and resilience, qualities that I believe define a successful professional in any field but especially computer science.


#### What is MyMessierTracker?
MyMessierTracker is a full-stack Flask + PostgreSQL web app that lets you catalog your Messier captures, upload a photo, tag the object, add notes, and track progress across all 110 objects with clean analytics and visuals. It also includes real catalog data (object types, RA/Dec location, magnitude) with rarity scores and progress metrics. It aims to help users track and journal their Messier-object observations while inspiring astrophotographers to continue gazing upward and capturing the wonders of the night sky.


## Code Review
Here I discuss the code behind the web app, the structure of the database and the planned development of enhancements.

<div style="position:relative; padding-bottom:56.25%; height:0; overflow:hidden; max-width:100%;">
  <iframe
    src="https://www.youtube-nocookie.com/embed/fyCA9lOTE8Y"
    title="YouTube video player"
    style="position:absolute; top:0; left:0; width:100%; height:100%; border:0;"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
    referrerpolicy="strict-origin-when-cross-origin"
    allowfullscreen>
  </iframe>
</div>

You can find my original code and enhanced code files here.

/* buttons to navigate to code files */
<div style="display:flex;gap:12px;flex-wrap:wrap">
  <a href="https://[github.com/<you>/<repo>/tree/main/path/to/folderA](https://github.com/StellarNavi/StellarNavi.github.io/blob/main/Original%20Code%20Files)"
     target="_blank" rel="noopener"
     style="padding:10px 16px;border-radius:8px;border:1px solid #444;text-decoration:none;font-weight:600;background:#1f2328;color:#fff">
    Folder A
  </a>
  <a href="https://[github.com/<you>/<repo>/tree/main/path/to/folderB](https://github.com/StellarNavi/StellarNavi.github.io/blob/main/Updated%20Files)"
     target="_blank" rel="noopener"
     style="padding:10px 16px;border-radius:8px;border:1px solid #444;text-decoration:none;font-weight:600;background:#1f2328;color:#fff">
    Folder B
  </a>
</div>


## Personal Self-Assessment


## Program-wide self-assessment
* Collaborating in a team environment: Used feature branches (enh1/2/3 → dev → main), performed merges with conflict resolution, and documented changes for review—habits that translate directly to team workflows.
* Communicating with stakeholders: Explain requirements and trade-offs in non-jargon terms (e.g., why a normalized schema + views beats ad-hoc queries; why secure uploads matter) and maintain concise READMEs/runbooks.
* Data structures & algorithms: Applied indexing strategies, window functions, and efficient server-side computations to keep UI snappy and metrics correct at scale.
* Software engineering & database: Produced a maintainable Flask codebase, reproducible Docker setup, migration/seed SQL, and templated UI—demonstrating full-stack competency.
* Security mindset: Practiced defense-in-depth (hashed credentials, validated inputs, safe file paths, secret management) and considered abuse cases (path traversal, CSRF, weak passwords).

### How the artifact enhancements fit together
  I chose to develop and enhance a singluar project to show how these topics all fit together in a project as a whole.
  
  * Authentication & Accounts (Enhancement 1): Secure login/registration establishes identity and protects user data.
  * Analytics & Rarity Metrics (Enhancement 2): SQL views and calculated fields power charts/insights visible in the dashboard.
  * Edit/Delete & Journal UX (Enhancement 3): Robust CRUD with safe image handling and consistent UI patterns completes the end-to-end user workflow.
  * Together they illustrate a coherent product: secure users, trustworthy data, and a polished interface deployed like real software.

## Enhancement Narratives

### The artifact used for all three enhancements that I will discuss here was my custom full-stack web application - 'My Messier Tracker'
