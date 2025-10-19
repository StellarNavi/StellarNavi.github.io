#this is in progress....
<p>Hello 👋 I’m <strong>Audrey Weaver</strong>, and I am completing my <strong>Bachelor of Science in Computer Science</strong> with a concentration in <strong>Data Analytics</strong>. Over the course of this program, I have developed both the technical depth and professional confidence to design, build, troubleshoot, and deliver impactful software solutions.</p>

<p>This ePortfolio, which features my custom capstone project <a href="https://mymessiertracker.com" target="_blank" rel="noopener"><strong>My Messier Tracker</strong></a>, demonstrates my ability to apply computer science principles to solve meaningful problems through full-stack development, database engineering, and data visualization. Early coursework in algorithms and data structures strengthened my logical problem-solving foundation, while later courses emphasized secure, modular software and well-documented database design.</p>

<p>The <em>My Messier Tracker</em> project is a culmination of these skills. It is a full-stack web application that allows users to track, document, and analyze their astrophotography progress across the Messier catalog. The project integrates a PostgreSQL database, Flask back end, and interactive front end featuring real user data and visualizations. Through this process, I demonstrated proficiency in software engineering, database optimization, user authentication, and security design.</p>

<p>Collaboration and communication have been central to my success in this program. I have worked in agile-style environments, managed code versions through Git and GitHub, and practiced clear documentation through peer reviews and project artifacts. These experiences have prepared me to thrive in dynamic, cross-functional teams and to communicate technical insights effectively to both technical and non-technical audiences.</p>

<p>My ePortfolio showcases three major enhancements representing the core areas of computer science: <strong>software engineering</strong>, <strong>algorithms and data structures</strong>, and <strong>databases</strong>. Collectively, these artifacts demonstrate my ability to turn well-designed ideas into production-ready applications that deliver value. As I enter the next stage of my career, I bring a passion for data-driven problem solving, continuous learning, and building solutions that balance innovation with security and performance.</p>


#### What is MyMessierTracker?
MyMessierTracker is a full-stack Flask + PostgreSQL web app that lets you catalog your Messier captures, upload a photo, tag the object, add notes, and track progress across all 110 objects with clean analytics and visuals. It also includes real catalog data (object types, RA/Dec location, magnitude) with rarity scores and progress metrics. It aims to help users track and journal their Messier-object observations while inspiring astrophotographers to continue gazing upward and capturing the wonders of the night sky.

You can access <a href="https://mymessiertracker.com" target="_blank" rel="noopener"><strong>My Messier Tracker</strong></a> by creating your own account or exploring it with some data already populated for your convinience by using the demo account creditials below:

<p align="center">
UN: demo@pending.com
PW: 123 
</p>

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
* Collaborating in a team environment: Used feature branches (enh1/2/3 → dev → main), performed merges with conflict resolution, and documented changes for review, these are all habits that translate directly into a real-world team workflows.
* Communicating with stakeholders: Explain requirements and trade-offs in a way that both technical and non-technical audiences can follow (examples: why a normalized schema + views are more efficient than ad-hoc queries, why secure uploads matter and practiced maintaining concise READMEs and other documentation).
* Data structures & algorithms: Applied indexing strategies, window functions, choosing the best algorithm for the need and implementing efficient server-side computations to keep UIs snappy and real-time metrics accurate at scale.
* Software engineering & database: Produced an easily maintainable Flask codebase, reproducible Postgres database structure with easilly seedable SQL, modularized code with a  templated UI - demonstrating full-stack competency.
* Security mindset: Practiced a security mindset throughout the entire process with strongly hashed credentials, validated inputs, safe file paths, secret management and considered abuse cases such as path traversal, and CSRF (cross-site request forgery) through requiring the users passwords at destructive action requests even thorugh authentication during the current session is already active.

### How the artifact enhancements fit together
  I chose to develop and enhance a singluar project to show how these topics all fit together in a project as a whole.
  
  * Authentication & Accounts (Enhancement 1): Secure login/registration establishes identity and protects user data.
  * Analytics & Rarity Metrics (Enhancement 2): SQL views and calculated fields power charts/insights visible in the dashboard.
  * Edit/Delete & Journal UX (Enhancement 3): Robust CRUD with safe image handling and consistent UI patterns completes the end-to-end user workflow.
  * Together they illustrate a coherent product: secure users, trustworthy data, and a polished interface deployed like real software.

## Enhancement Narratives

### Software Design and Engineering: Implementing Account Deletion Functionality
<p>I implemented a secure “Delete My Account” flow that permanently removes a user and all related data, aligning the app with privacy best practices (<a href="https://gdpr-info.eu/art-17-gdpr/" target="_blank" rel="noopener">Right to Erasure</a>) while keeping the codebase lean and maintainable.</p>

- A user can choose to delete account data from their profile menu.
<p align="center">
  <img width="319" height="251" alt="image" src="https://github.com/user-attachments/assets/60925572-0c4a-4f4f-a259-751058d9a64c" />
</p>

- Here they will be given a clear warning that this action is final and irreversible. A password is required to confirm this decision.
<p align="center">
  <img width="319" height="251" alt="image" src="https://github.com/user-attachments/assets/348da4aa-57a4-4b68-97ee-c8774b502628" />
</p>

- Once they enter their password then all data is deleted in proper order through a cascading SQL structure that also collects all files stored and later deletes those files as well once the database records are removed.

```python
# DELETE ACCOUNT PAGE VIEW -------------------------------------------------------------------------
@app.route("/account/delete", methods=["POST"])
@login_required
def account_delete():
    # pulled from delete modal password input
    pwd = request.form.get("delete_acct_password", "")
    user_id = str(current_user.id)

    # open db connection
    conn = get_db_conn()
    # placeholder for files to collect then delete
    file_paths = []
    try:
        with conn.cursor() as cur:
            # Verify password
            cur.execute("""SELECT password_hash 
                        FROM public.users WHERE id = %s""", (user_id,))
            row = cur.fetchone()
            # bad password
            if not row or not row[0] or not bcrypt.check_password_hash(row[0], pwd):
                flash("Incorrect password. Please try again.", "danger")
                session['del_error'] = "Incorrect password. Please try again"
                return redirect(url_for("dashboard", del_error=1))

            # pass userid & get image paths before deleting from table so they can be removed later
            cur.execute("SELECT file_path FROM public.images WHERE user_id = %s", (user_id,))
            img_files = [r[0] for r in cur.fetchall()]

            # delete all user data via cascades generated at schema creation, this setup properly 
            # manages the removal of records from journal_entries, user_object_images, images tables
            cur.execute("DELETE FROM public.users WHERE id = %s", (user_id,))

        # commits changes to db
        conn.commit()
        
    # if process failed, let user know and send back to dashboard page and close db connection    
    except Exception:
        if conn: conn.rollback()
        # error then shown in the delete modal setup in index.html
        return redirect(url_for("dashboard"))
    finally:
        if conn:
            conn.close()

    # then remove actual image files from storage
    for img in img_files:
        try:
            # updated to be platform agnositic for web service deployment
            # TODO: VALIDATE
            p = (UPLOAD_DIR / img)
            if p.exists():
                p.unlink()
        except Exception:
            app.logger.exception("Failed to delete file %s", img)

    # send user to the 'success' screen and logout
    logout_user()
    return render_template("post_delete.html")
  ```
    
- The completion of this process is confirmed to the user once complete.
<p align="center">
  <img width="319" height="251" alt="image" src="https://github.com/user-attachments/assets/8627c18c-56bf-489b-a715-bf1ffdc9f3f6" />
</p>


### The artifact used for all three enhancements that I will discuss here was my custom full-stack web application - 'My Messier Tracker'
