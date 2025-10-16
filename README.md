# StellarNavi.github.io

Hello 👋 I'm Audrey and I am wrapping up my bachelors of science in Computer Science with a concentration in Data Analytics. I'm happy to share my custom, full-stack web application titled <a href="https://www.mymessiertracker.com/" target="_blank" rel="noopener noreferrer">My Messier Tracker</a> as proof of my skills in the field of computer science. 

#### What is MyMessierTracker?
MyMessierTracker is a full-stack Flask + PostgreSQL web app that lets you catalog your Messier captures, upload a photo, tag the object, add notes, and track progress across all 110 objects with clean analytics and visuals. It also includes real catalog data (object types, RA/Dec location, magnitude) with rarity scores and progress metrics. It aims to help users track and journal their Messier-object observations while inspiring astrophotographers to continue gazing upward and capturing the wonders of the night sky.

---

### Code Review
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

You can find my original code files here and the final enhancements made

## Personal Self-Assessment


### Program-wide self-assessment

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
