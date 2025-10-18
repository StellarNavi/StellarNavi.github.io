#this is in progress....
<p>Hello 👋 I’m <strong>Audrey Weaver</strong>, and I am completing my <strong>Bachelor of Science in Computer Science</strong> with a concentration in <strong>Data Analytics</strong>. Over the course of this program, I have developed both the technical depth and professional confidence to design, build, troubleshoot, and deliver impactful software solutions.</p>

<p>This ePortfolio, which features my custom capstone project <a href="https://mymessiertracker.com" target="_blank" rel="noopener"><strong>My Messier Tracker</strong></a>, demonstrates my ability to apply computer science principles to solve meaningful problems through full-stack development, database engineering, and data visualization. Early coursework in algorithms and data structures strengthened my logical problem-solving foundation, while later courses emphasized secure, modular software and well-documented database design.</p>

<p>The <em>My Messier Tracker</em> project is a culmination of these skills. It is a full-stack web application that allows users to track, document, and analyze their astrophotography progress across the Messier catalog. The project integrates a PostgreSQL database, Flask back end, and interactive front end featuring real user data and visualizations. Through this process, I demonstrated proficiency in software engineering, database optimization, user authentication, and security design.</p>

<p>Collaboration and communication have been central to my success in this program. I have worked in agile-style environments, managed code versions through Git and GitHub, and practiced clear documentation through peer reviews and project artifacts. These experiences have prepared me to thrive in dynamic, cross-functional teams and to communicate technical insights effectively to both technical and non-technical audiences.</p>

<p>My ePortfolio showcases three major enhancements representing the core areas of computer science: <strong>software engineering</strong>, <strong>algorithms and data structures</strong>, and <strong>databases</strong>. Collectively, these artifacts demonstrate my ability to turn well-designed ideas into production-ready applications that deliver value. As I enter the next stage of my career, I bring a passion for data-driven problem solving, continuous learning, and building solutions that balance innovation with security and performance.</p>


#### What is MyMessierTracker?
MyMessierTracker is a full-stack Flask + PostgreSQL web app that lets you catalog your Messier captures, upload a photo, tag the object, add notes, and track progress across all 110 objects with clean analytics and visuals. It also includes real catalog data (object types, RA/Dec location, magnitude) with rarity scores and progress metrics. It aims to help users track and journal their Messier-object observations while inspiring astrophotographers to continue gazing upward and capturing the wonders of the night sky.


## Code Review
Here I discuss the code behind an early version of the web app, the structure of the database and the planned development of enhancements. Below you can also find the code files for this earlier version as well as the code files after the enhancements were published.

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

<p></p>

<p align="center">You can find my original code and enhanced code files here.</p>

<div class="d-flex justify-content-center gap-2 flex-wrap"
     style="display:flex;justify-content:center;gap:12px;flex-wrap:wrap;width:100%;margin:16px 0;">
  <a href="https://github.com/StellarNavi/StellarNavi.github.io/tree/main/Original%20Code%20Files"
     target="_blank" rel="noopener"
     style="display:inline-flex;align-items:center;justify-content:center;
            padding:10px 16px;border-radius:8px;border:1px solid #444;
            text-decoration:none;font-weight:600;background:#1f2328;color:#fff">
    Original Code Files
  </a>

  <a href="https://github.com/StellarNavi/StellarNavi.github.io/tree/main/Updated%20Files"
     target="_blank" rel="noopener"
     style="display:inline-flex;align-items:center;justify-content:center;
            padding:10px 16px;border-radius:8px;border:1px solid #444;
            text-decoration:none;font-weight:600;background:#1f2328;color:#fff">
    Enhanced Code Files
  </a>
</div>



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
