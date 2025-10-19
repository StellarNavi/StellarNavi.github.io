## Table of Contents
- [Professional Self-Assessment](#professional-self-assessment)
  - [Demonstrating Professional Competencies](#demonstrating-professional-competencies)
  - [What is MyMessierTracker?](#what-is-mymessiertracker)   
- [Code Review](#code-review)
- [Enhancement Narratives](#enhancement-narratives)
  - [Software Design and Engineering: Implementing Account Deletion Functionality](#software-design-and-engineering-implementing-account-deletion-functionality)
  - [Algorithms and Data Structures: Implementing a Rarity Score Metric](#algorithms-and-data-structures-implementing-a-rarity-score-metric)
  - [Databases: Complete CRUD Operations](#databases-complete-crud-operations)
- [Thank You](#thank-you)

## Professional Self-Assessment

<p>Hello 👋 I’m <strong>Audrey Weaver</strong>, and I am completing my <strong>Bachelor of Science in Computer Science</strong> with a concentration in <strong>Data Analytics</strong>. Over the course of this program, I have developed both the technical depth and professional confidence to design, build, troubleshoot, and deliver impactful software solutions.</p>

<p>This ePortfolio, which features my custom capstone project <a href="https://mymessiertracker.com" target="_blank" rel="noopener"><strong>My Messier Tracker</strong></a>, demonstrates my ability to apply computer science principles to solve meaningful problems through full-stack development, database engineering, and data visualization. Early coursework in algorithms and data structures strengthened my logical problem-solving foundation, while later courses emphasized secure, modular software and well-documented code. This project integrates a PostgreSQL database, Flask back end, and interactive front end featuring real user data and real-time visualizations. Through this process, I demonstrated proficiency in software engineering, database optimization, and secure application design.</p>

<p>Collaboration and communication have been central to my success in this program. I have worked in agile-style environments, managed code versions through Git and GitHub, and practiced clear documentation, both written and verbal. These experiences have prepared me to thrive in dynamic, cross-functional teams and to communicate technical insights effectively to both technical and non-technical audiences.</p>

<p>My ePortfolio showcases three major enhancements representing the core areas of computer science: <strong>software engineering</strong>, <strong>algorithms and data structures</strong>, and <strong>databases</strong>. Collectively, these artifacts demonstrate my ability to turn well-designed ideas into production-ready applications that deliver value. As I enter the next stage of my career, I bring a passion for data-driven problem solving, continuous learning, and building solutions that balance innovation with security and performance.</p>

### Demonstrating Professional Competencies
* **Collaborating in a team environment:** Used feature branches (enh1/2/3 → dev → main), performed merges with conflict resolution, and documented changes for review, these are all habits that translate directly into a real-world workflows within a team environment.
* **Communicating with stakeholders:** Explain requirements and trade-offs in a way that both technical and non-technical audiences can follow (examples: why a normalized schema + views are more efficient than ad-hoc queries or costly loops, why security matters at every step and practiced maintaining concise READMEs, code comments and other documentation).
* **Data structures & algorithms:** Applied indexing strategies, window functions, choosing the best algorithm for the need and implementing efficient server-side computations to keep UIs snappy and real-time metrics accurate at scale.
* **Software engineering & database:** Produced an easily maintainable Flask codebase, reproducible Postgres database structure with easily seedable SQL and modularized code with a templated user interface that is easy to maintain demonstrating full-stack competency.
* **Security mindset:** Practiced a security mindset throughout the entire process with strongly hashed credentials, validated inputs, safe file paths and considered abuse cases such as path traversal, and CSRF (cross-site request forgery) through requiring the users passwords at destructive action requests even thorugh authentication during the current session is already active.

#### What is MyMessierTracker?
I chose to develop this project to show how these topics all fit together in a singular project as a whole. Together these illustrate a polished product that is secure for managing user data and providing a meaningful and reliable tool within a modern, easy to use interface. MyMessierTracker is a full-stack Flask + PostgreSQL web app that lets you catalog your captures of the Messier DSOs (deep-sky objects), upload a photo, tag the object, add notes, and track progress across all 110 objects with clean analytics and visuals. It also includes real catalog data (object types, RA/Dec location, magnitude) with rarity scores and progress metrics. It aims to help users track and journal their Messier-object observations while inspiring astrophotographers to continue gazing upward and capturing the wonders of the night sky. 

You can access <a href="https://mymessiertracker.com" target="_blank" rel="noopener"><strong>My Messier Tracker</strong></a> by creating your own account or exploring it with some data already populated for your convenience by using the following demo account credentials: EMAIL=demo@mymessiertracker.com and PW=demo1.

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





## Enhancement Narratives

### Software Design and Engineering: Implementing Account Deletion Functionality
<p>I implemented a secure “Delete My Account” flow that permanently removes a user and all related data, aligning the app with privacy best practices (<a href="https://gdpr-info.eu/art-17-gdpr/" target="_blank" rel="noopener">Right to Erasure</a>) while keeping the codebase lean and maintainable. *Please note that if you are using the demo account proeviously provided and want to test this functionality that it will delete the demo account so you may want to explore the other enhancements frst with this demo data before doing so.* </p>

- A user can choose to delete account data from their profile menu.
<p align="center">
  <img src="https://github.com/user-attachments/assets/60925572-0c4a-4f4f-a259-751058d9a64c" alt="image" width="300" style="height:auto;" />
</p>

- Here they will be given a clear warning that this action is final and irreversible. A password is required to confirm this decision.
<p align="center">
  <img src="https://github.com/user-attachments/assets/348da4aa-57a4-4b68-97ee-c8774b502628" alt="image" width="360" style="height:auto;"/>
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
    
- This process is confirmed to the user once complete.
<p align="center">
  <img alt="image" src="https://github.com/user-attachments/assets/8627c18c-56bf-489b-a715-bf1ffdc9f3f6" alt="image" width="380" style="height:auto;"/>
</p>

### Algorithms and Data Structures: Implementing A Rarity Score Metric
<p>This enhancement included generating an efficient computation for identifying the object rarity across all journals of all users. Here I focused on data structures and algorithms where I designed an object rarity metric to help encourage users to keep logging their observations. The goal was to make it fun through tooltips to help quickly identify some of the most popular objects that the user has not yet collected as well as reward them in their journal with a star when they have captured something fewer users have. </p>

-	A new database view leveraging indexes and joins was created that computes the rarity of each object in one grouped process over `user_object_images` and distinct user counts. This avoids per-object (`N+1`) SQL scans or Python loops. The complexity is `O(U + I + M·log M)` since `M = 110` is constant, it reduces to `O(U + I)` time and `O(1)` space.
  
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
-	The user can now mouseover every chart on the page to get a list of the ‘Top 3’ objects remaining that are most popular in each category (or overall). This is sorted by most popular descending. *Please note that the values on these tooltips may seem too round and consistent, that is because there are not that many user accounts in the system, but as the user base grows these numbers would start to appear more realistic*.
<p align="center">
  <img alt="image" src="https://github.com/user-attachments/assets/85bfba2d-694a-4589-b493-11ddf412e2e2" alt="image" width="720" style="height:auto;"/>
</p>

- And once the user has captured all objects in a category their mouseover will update to display a ‘Congrats’ message.
<p align="center">
  <img alt="image" src="https://github.com/user-attachments/assets/b6f8a58b-bb1b-4559-bee0-abad4e43acf8" alt="image" width="360" style="height:auto;" />
</p>
- Additionally, the user can also see their top most rare objects that they have already captured (with the constraint that the objects rarity is below 50%)
<p align="center">
  <img alt="image" src="https://github.com/user-attachments/assets/2a171201-f58a-4fdb-8c49-703e1599dfc4" alt="image" width="390" style="height:auto;"/>
</p>

### Databases: Complete CRUD Operations 
<p>Here I completed the CRUD operations by adding functionality for the user to edit and remove journal entries. The user could already create records by adding new object entries to their Messier Journal and inserting them into the database and they could also read from the database all of the data they had previously loaded, plus some additional object information. However, they were unable to edit their entries or completely remove an entry until this enhancement. Even though this enhancement was focused on databases, all of my enhancements have had a heavy focus on proper database schema design, scalability and ensuring that the application has secure interactions with the database.</p>

<p align="center">
  <img alt="image" src="https://github.com/user-attachments/assets/cc55fa41-e142-4c3a-b9f5-c85b03939d25" alt="image" width="500" style="height:auto;"/>
</p>

<p>I selected this enhancement to showcase a secure and computationally efficient mindset when designing and interacting with databases. When a user clicks on either edit or delete buttons, the system collects their user_id and entry_id as variables to be used in the respective queries that will ensure the correct record is being edited or deleted. This setup will also handle in cases where there may be a system error and will not allow any further steps in the process to take place if the entry id cannot be confirmed.</p>

```python
  # TODO Journal Entry Delete function ---------------------------------------------------------------
  @app.route("/journal/delete", methods=["POST"])
  @login_required
  def journal_delete():
      user_id = str(current_user.id)
      entry_id = request.form.get("entry_id", "")

    # if there is an issue collecting the entry id then flash error and send back to dashboard
    if not entry_id:
        flash("Missing entry id.", "danger")
        return redirect(url_for("dashboard"))
    
    conn = get_db_conn()
    cur = conn.cursor()
```
- If the user clicks on the edit icon then the user get the option to edit one or all elements of their original entry

<p align="center">
  <img alt="image" src="https://github.com/user-attachments/assets/cc55fa41-e142-4c3a-b9f5-c85b03939d25" alt="image" width="500" style="height:auto;"/>
</p>

- One thing I came across here was needing to make sure that I also passed all of the previous data elements that were loaded into the system already instead of blank by default, else when the user when to save their entry but say only updated the date field, the journal notes would be completely erased as the original notes were not persisting. However, I made sure to make that change and as you can see in the image above these are the previous values pop-up correctly allowing the user to review their data before saving any changes to ensure nothing is lost in the process. Once the user has confirmed their changes, then the system performs an UPDATE statement and brings the user back to their dashboard.

```python
# update date/notes and get updated timestamp
            cur.execute("""
                UPDATE public.journal_entries
                SET observed_date = %s,
                    body = %s,
                    updated_at = NOW()
                WHERE id = %s AND user_id = %s
            """, (obs_date, body_text, entry_id, user_id))
```

- If the user clicks on the delete icon then they are prompted with a warning similar to the user account deletion process for consistency. This ensures that they are well-informed that this action is permanent and irreversible.
<p align="center">
  <img alt="image" src="https://github.com/user-attachments/assets/46779a62-2abc-4a6e-b7f8-1c79d8f906aa" alt="image" width="500" style="height:auto;"/>
</p>


- The code for this process collects the entry id and passes it along with the user id within a DELETE statement to remove the journal entry record as well as related records for images then also removes the  image from storage.
```python
    # DELETE ALL DATABASE RECORDS
    # delete the journal entry
    cur.execute("""DELETE 
                   FROM public.journal_entries 
                   WHERE id = %s AND user_id = %s ;""",
                (entry_id, user_id))


    # TODO remove record from user_object_images
    cur.execute("""DELETE 
                FROM public.user_object_images 
                WHERE image_id = %s AND user_id = %s ;""",
                (img_id, user_id))

    # TODO remove record from images
    cur.execute("""DELETE 
                FROM public.images 
                WHERE id = %s AND user_id = %s ;""",
                (img_id, user_id))
    conn.commit()
```
- Then it ensures the corresponding img is deleted from the file storage as well

```python
    # DELETE FROM FILE STORAGE
    # TODO remove image file from file storage
    try:
        # updated to be platform agnostic for web service deployment
        # TODO: VALIDATE
        p = (UPLOAD_DIR / img_key)
        if p.exists():
            p.unlink()
    except Exception:
        app.logger.exception("Failed to delete file %s", p)

    return redirect(url_for("dashboard"))
```

## Thank You
<p align="center">
  <img alt="image" src="https://github.com/user-attachments/assets/a1cff61c-3dae-4cf0-897d-ac81f27dd69b" alt="image" width="360" style="height:auto;"/>
</p>
Thank you for taking the time to view my project. There is so much more I would like to add to it in the future! If you have any questions or suggestions for future enhancements please feel free to reach out to me at audrey․weaver00@live․com.
