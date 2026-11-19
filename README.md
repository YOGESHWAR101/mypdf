### Part A: Access Moodle Cloud

Open Moodle, log in, and explore the dashboard.

### Part B: Analyze the Architecture

Identify the layers and data flow.

### Part C: Create a Course Category

Create and save a category.

### Part D: Create a Course

Create a course and assign its category.

### Part E: Manage Users

Create student and teacher accounts.

### Part F: Enrol Users

Enrol a student in the course.

### Part G: Add Resources

Add topics, resources, quiz, and assignment.

### Part H: Verify Entities

Check the course, users, and activities.



2222
### Step 1: Install XAMPP

Download and install XAMPP.

### Step 2: Start Services

Start Apache and MySQL.

### Step 3: Create Database

Create `wordpress_db` in phpMyAdmin.

### Step 4: Install WordPress

Download WordPress, extract it into `htdocs`, and open it.

### Step 5: Configure WordPress

Enter database details and create an admin account.

### Step 6: Create Website

Create and publish Home, About, Services, Blog, and Contact pages.

### Step 7: Social Marketing

Add social media links and publish a blog post.

### Step 8: Configure SEO

Add keywords, meta descriptions, and image alt text.

### Step 9: Add Sharing Tools

Install a sharing plugin and enable social buttons.

### Step 10: Test Website

Check pages, links, SEO, and sharing features.




4444
### Step 1: Open Codenvy

Open Codenvy, sign in, and explore the dashboard.

### Step 2: Create Workspace

Create `WebsiteScalingLab` and start the workspace.

### Step 3: Create Website

Create a project, add `index.html`, and save the code.

### Step 4: Run Website

Start the server and test the website.

### Step 5: Demonstrate Provisioning

Check resources, modify settings if possible, restart, and test.






aiiiiiiiiiiiiiiiiiiiiiiiiiii

Below are all 4 Prolog practical programs in exam format:
1.	Program Name
2.	Complete Code
3.	Query to Execute
4.	Expected Output
You can copy these directly into your practical notebook.
1. Basic Prolog Program and Temperature Conversion
Complete Code:
likes(ram,mango).
likes(bill,cindy).
girl(seema).
red(rose).
owns(john,gold).

% Celsius to Fahrenheit
c_to_f(C,F):-
    F is (C*9/5)+32.

% Below freezing
below_freezing(C):-
    C=<0.

% Fahrenheit to Celsius
f_to_c(F,C):-
    C is (F-32)*5/9.
Queries and Output:
Query 1:
?- likes(ram,mango).
Output:
true.
Query 2:
?- likes(ram,What).
Output:
What = mango.
Query 3:
?- red(What).
Output:
What = rose.
Query 4:
?- owns(Who,What).
Output:
Who = john,
What = gold.
Query 5:
?- c_to_f(100,F).
Output:
F = 212.
Query 6:
?- f_to_c(212,C).
Output:
C = 100.
Query 7:
?- below_freezing(-5).
Output:
true.
2. Eight Queens Problem
Complete Code:
queens(Solution):-
    permutation([1,2,3,4,5,6,7,8],Solution),
    safe(Solution).

safe([]).

% Take one queen and check it with all remaining
safe([Queen|Rest]):-
    check(Queen,Rest,1),
    safe(Rest).

% No queens to check
check(_,[],_).

% Not in same row and column
check(Queen,[Next|Rest],Distance):-
    Queen=\=Next,

    % Check not on same diagonal
    abs(Queen-Next)=\=Distance,

    % Increase column distance
    D is Distance+1,

    % Check with next queen
    check(Queen,Rest,D).
Query:
?- queens(Solution).
Expected Output (one valid solution):
Solution = [1,5,8,6,3,7,2,4].
Note: The order of solutions can vary depending on the Prolog implementation.
3. Depth First Search (DFS)
Complete Code:
solve(Node,Solution):-
    depthfirst([],Node,Solution).

% depthfirst(Path,Node,Solution).

depthfirst(Path,Node,[Node|Path]):-
    goal(Node).

depthfirst(Path,Node,Sol):-
    edge(Node,Node1),
    not(member(Node1,Path)),
    depthfirst([Node|Path],Node1,Sol).

% Edges
edge(1,3).
edge(2,4).
edge(3,5).
edge(5,6).

% Goal
goal(6).
Query:
?- solve(1,Solution).
Output:
Solution = [6,5,3,1].
4. Best First Search
Complete Code:
edge(a,b).
edge(a,c).
edge(b,d).
edge(c,e).
edge(d,g).
edge(e,g).

h(b,4).
h(c,2).
h(d,3).
h(e,1).
h(g,0).

best_first(Start,Goal,Path):-
    search([(Start,[Start])],Goal,Path).

search([(Goal,Path)|_],Goal,Path).

search([(Node,Path)|Rest],Goal,Solution):-
    findall((H,Next,[Next|Path]),
        (edge(Node,Next),h(Next,H)),
        Children),

    append(Rest,Children,Open),
    sort(Open,Sorted),
    search_nodes(Sorted,Goal,Solution).

search_nodes([(_,Node,Path)|Rest],Goal,
    Solution):-
    search_nodes([(Node,Path)|Rest],Goal,Solution).

search_nodes([(_,Node,Path)|Rest],Goal,
    Solution):-
    search([(Node,Path)|Rest],Goal,Solution).

search_nodes([(Node,Path)|Rest],Goal,
    Solution):-
    search([(Node,Path)|Rest],Goal,Solution).
Important correction: Use the following search_nodes definition instead of the three definitions above:
search_nodes([(H,Node,Path)|Rest],Goal,Solution):-
    search([(Node,Path)|Rest],Goal,Solution).
Query:
?- best_first(a,g,Path).
Output:
Path = [g,e,c,a].
Quick revision for practical exam
No.	Program name	Query
1	Basic Prolog	?- likes(ram,mango).
2	Eight Queens	?- queens(Solution).
3	DFS	?- solve(1,Solution).
4	Best First Search	?- best_first(a,g,Path).
Exam tip: First save the complete code in the Program editor. Then execute the query in the Query/Goal section. The output will appear below.
  
 
        

