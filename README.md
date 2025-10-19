#this is in progress....
<p>Hello 👋 I’m <strong>Audrey Weaver</strong>, and I am completing my <strong>Bachelor of Science in Computer Science</strong> with a concentration in <strong>Data Analytics</strong>. Over the course of this program, I have developed both the technical depth and professional confidence to design, build, troubleshoot, and deliver impactful software solutions.</p>

<p>This ePortfolio, which features my custom capstone project <a href="https://mymessiertracker.com" target="_blank" rel="noopener"><strong>My Messier Tracker</strong></a>, demonstrates my ability to apply computer science principles to solve meaningful problems through full-stack development, database engineering, and data visualization. Early coursework in algorithms and data structures strengthened my logical problem-solving foundation, while later courses emphasized secure, modular software and well-documented code. This project integrates a PostgreSQL database, Flask back end, and interactive front end featuring real user data and real-time visualizations. Through this process, I demonstrated proficiency in software engineering, database optimization, and secure application design.</p>

<p>Collaboration and communication have been central to my success in this program. I have worked in agile-style environments, managed code versions through Git and GitHub, and practiced clear documentation, both written and verbal. These experiences have prepared me to thrive in dynamic, cross-functional teams and to communicate technical insights effectively to both technical and non-technical audiences.</p>

<p>My ePortfolio showcases three major enhancements representing the core areas of computer science: <strong>software engineering</strong>, <strong>algorithms and data structures</strong>, and <strong>databases</strong>. Collectively, these artifacts demonstrate my ability to turn well-designed ideas into production-ready applications that deliver value. As I enter the next stage of my career, I bring a passion for data-driven problem solving, continuous learning, and building solutions that balance innovation with security and performance.</p>


#### What is MyMessierTracker?
MyMessierTracker is a full-stack Flask + PostgreSQL web app that lets you catalog your Messier captures, upload a photo, tag the object, add notes, and track progress across all 110 objects with clean analytics and visuals. It also includes real catalog data (object types, RA/Dec location, magnitude) with rarity scores and progress metrics. It aims to help users track and journal their Messier-object observations while inspiring astrophotographers to continue gazing upward and capturing the wonders of the night sky.

You can access <a href="https://mymessiertracker.com" target="_blank" rel="noopener"><strong>My Messier Tracker</strong></a> by creating your own account or exploring it with some data already populated for your convinience by using the following demo account creditials: UN=demo@pending.com and PW=123.

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

<p align="center">You can find my original and enhanced code files here.</p>

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



### Program-wide self-assessment
* Collaborating in a team environment: Used feature branches (enh1/2/3 → dev → main), performed merges with conflict resolution, and documented changes for review, these are all habits that translate directly into a real-world team workflows.
* Communicating with stakeholders: Explain requirements and trade-offs in a way that both technical and non-technical audiences can follow (examples: why a normalized schema + views are more efficient than ad-hoc queries, why secure uploads matter and practiced maintaining concise READMEs and other documentation).
* Data structures & algorithms: Applied indexing strategies, window functions, choosing the best algorithm for the need and implementing efficient server-side computations to keep UIs snappy and real-time metrics accurate at scale.
* Software engineering & database: Produced an easily maintainable Flask codebase, reproducible Postgres database structure with easilly seedable SQL, modularized code with a  templated UI - demonstrating full-stack competency.
* Security mindset: Practiced a security mindset throughout the entire process with strongly hashed credentials, validated inputs, safe file paths, secret management and considered abuse cases such as path traversal, and CSRF (cross-site request forgery) through requiring the users passwords at destructive action requests even thorugh authentication during the current session is already active.

### How the artifact enhancements fit together
  I chose to develop and enhance a singluar project to show how these topics all fit together in a project as a whole. Together these illustrate a polished product that is secure and trustworthy for managing user data and providing a meaningful and reliable tool within a modern and easy to use interface.
  
  * Engineering Ethical and Secure Account Management (Enhancement 1): Secure login/registration establishes identity and protects user data.
  * Providing Robust & Efficient Analytics & Metrics (Enhancement 2): SQL views and calculated fields power charts/insights visible in the dashboard.
  * Implementing Scalable CRUD Operations (Enhancement 3): Robust CRUD with safe image handling and consistent UI patterns completes the end-to-end user workflow.

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

### Algorithms and Data Structures: Implementing A Rarity Score Metric
<p>included generating an efficient computation for identifying the object rarity across all journals of all users.</p>

-	A new database view leveraging indexes and joins was created that computes the rarity of each object in one grouped process over user_object_images and single user counts. This avoids counting per object/N+1 queries in SQL or inefficient loops in Python. This essentially results in \O(U+I+ M\log M)\) where U indicates the rows in the users table, I as rows in user_object_images and M as the rows in the messier_objects table. Since M is constant at 110, this can simplify to O(U+I) and \(O(1)\) in memory so it’s an efficient, speedy and resource friendly algorithm to compute this rarity metric.
  
```sql
WITH total_users AS (SELECT count(*)::numeric AS total_users
                     FROM users),
     obj AS (SELECT mo.id                                AS messier_id,
                    mo.messier_number,
                    mo.common_name,
                    mo.object_type,
                    count(DISTINCT uoi.user_id)::numeric AS user_ct
             FROM messier_objects mo
                      LEFT JOIN user_object_images uoi ON uoi.messier_id = mo.id
             GROUP BY mo.id, mo.messier_number, mo.common_name)
SELECT o.messier_id,
       o.object_type,
       (o.messier_number || ': '::text) || o.common_name AS object,
       CASE
           WHEN t.total_users = 0::numeric THEN 0::numeric
           ELSE round(100::numeric * o.user_ct / t.total_users, 2)
           END                                           AS rarity_pct
FROM obj o
         CROSS JOIN total_users t
ORDER BY (
             CASE
                 WHEN t.total_users = 0::numeric THEN 0::numeric
                 ELSE round(100::numeric * o.user_ct / t.total_users, 2)
                 END) DESC
```
-	Then since this was efficiently handled in the database portion of the app, the top N categorical queries can reference that view, pass the parameterized user id, sort and limit to N.

```python
# progress bar (top 3 overall)
cur.execute("""
    SELECT messier_id, object_type, object, rarity_pct
    FROM public.v_object_rarity
    WHERE messier_id NOT IN (
        SELECT uoi.messier_id
        FROM public.user_object_images AS uoi
        WHERE uoi.user_id = %s)
    ORDER BY rarity_pct DESC
    LIMIT 3;""", (user_id,))
capture_next = [{
        "messier_id": str(r[0]),
        "object_type": r[1],
        "object": r[2],
        "rarity_pct": r[3]
    } for r in cur.fetchall()]

# donut 1 (top 3 galaxies)
cur.execute("""
    SELECT messier_id, object_type, object, rarity_pct
    FROM public.v_object_rarity
    WHERE messier_id NOT IN (
        SELECT uoi.messier_id
        FROM public.user_object_images AS uoi
        WHERE uoi.user_id = %s)
      AND object_type = 'Galaxy'
    ORDER BY rarity_pct DESC
    LIMIT 3;""", (user_id,))
capture_next_galaxy = [{
        "messier_id": str(r[0]),
        "object_type": r[1],
        "object": r[2],
        "rarity_pct": r[3]}
    for r in cur.fetchall()]
```
-	These tooltips were then added to the index.html file and customized to be easily read and understood by the user.
-	The user can now mouseover every chart on the page to get a list of the ‘Top 3’ objects remaining that are most popular in each category (or overall). This is sorted by most popular descending.
<p align="center">
  <img width="319" height="251" alt="image" src="https://github.com/user-attachments/assets/85bfba2d-694a-4589-b493-11ddf412e2e2" />
</p>

- And once the user has captured all objects in a category their mouseover will update to display a ‘Congrats’ message.
<p align="center">
  <img width="319" height="251" alt="image" src="https://github.com/user-attachments/assets/b6f8a58b-bb1b-4559-bee0-abad4e43acf8" />
</p>
- Additionally, the user can also see their top most rare objects that they have already captured (with the constraint that the objects rarity is below 50%)
<p align="center">
<img width="319" height="251" alt="image" src="https://github.com/user-attachments/assets/2a171201-f58a-4fdb-8c49-703e1599dfc4" />
</p>


