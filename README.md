# Projects
## [My Forever Changing Website <span class="icon star"></span>](https://github.com/PantheraDigital/cloudflare-webpage)
![Screenshot of old version of this webpage.](https://raw.githubusercontent.com/PantheraDigital/InfoDump/refs/heads/main/project-imgs/PantheraDigital_PageScreenshot.webp)

The goal for this website has always been the same, a central place to display my projects, talk about them, and share other bits of knowledge with "posts".

Through its iterations I have explored different art styles and ways to accomplish the functionality I have desired. The previous iteration was hosted on GitHub Pages, allowing for only frontend JavaScript. This version first used Google API to pull text from Google Docs formatted with HTML and some custom HTML tags, parsed the text, then created and added elements to the HTML. After this it used GitHub API to pull the text data from a file in a repo formatted with markdown. 

In this latest iteration I have migrated to Cloudflare, allowing me to implement a true backend, bringing this site from pure frontend to full stack. 

#### Tech
- Frontend
  * HTML, JS, CSS
- Backend
  * Host ------- [Cloudflare](https://developers.cloudflare.com/)
  * Database --- [GitHub](https://github.com/)
  * Database --- [Cloudflare KV](https://developers.cloudflare.com/kv/)
  * Platform --- [Cloudflare Workers](https://developers.cloudflare.com/workers/)
  * MD to HTML - [Marked.js](https://marked.js.org/)

#### Website Features
<details>
 <summary>Server Side Rendering</summary>
 Using Cloudflare Workers this website has all of its content added before it is delivered to the client. Data is pulled from the sources, parsed, added to the HTML, then cached for future delivery.
</details>

<details>
 <summary>Remote Content Editing</summary>
 All content in "Projects" and "Posts" is pulled from a GitHub repo holding markdown text, parsed, then added to the page. By updating the GitHub files I can update what is shown here, without having to edit the website directly.
</details>

<details>
 <summary>Data Backup</summary>
 All relevant data is held in multiple locations, GitHub and Cloudflare KV Store. The KV Store acts as the primary database while GitHub is the fallback or original source.
</details>

<details>
 <summary>Render Caching</summary>
 To reduce work done in the backend, the rendered HTML is cached, along with a parsed version of the markdown data. This allows the website to deliver the latest version without rebuilding the site for every client request.
</details>

<details>
 <summary>HTML Template Files</summary>
 Due to Cloudflare Workers running on the JavaScript V8 engine, the backend lacks the ability to edit HTML in the same way frontend scripts do, such as using DOM. So HTML edits are done as plain text and typical HTML templates won't work for reused elements, such as the elements in the "Projects" and "Posts" sections. 

 To get around this I added a function that allows the backend to parse an HTML file as text, replace variable names that match with a JSON object's keys, and return a clean HTML structure as text that can be inserted into the main page's HTML. 

 This is similar to Angular.js templates and is where the inspiration came from.
</details>

<details>
 <summary>Automated Render Update</summary>
 When ever I update a file that would require a render update, a GitHub Webhook is triggered, alerting one of my Workers to re-render the website and cache the new result.
</details>

<details>
 <summary>MD to HTML Content</summary>
 By using Marked.js, I am able to convert the GitHub markdown text into usable HTML for injection into the website when rendering. 
</details>

#### Project Links
[My Website Worker](https://github.com/PantheraDigital/cloudflare-webpage/blob/main/scripts/index.js)
[My Secondary Worker Scripts](https://github.com/PantheraDigital/cloudflare-webpage-workers)
[The HTML Templates](https://github.com/PantheraDigital/cloudflare-webpage/tree/main/templates)
[The Content Repo](https://github.com/PantheraDigital/InfoDump)

[tags: Website]


## [Modular Character Controller <span class="icon play-arrow"></span>](https://github.com/PantheraDigital/Modular-Character-Controller-for-Godot)
![Icon for Godot Engine with an antenna.](https://raw.githubusercontent.com/PantheraDigital/InfoDump/refs/heads/main/project-imgs/PantheraDigital_ModularCharacterController.webp)

With my move to Godot I needed a new character controller. This time I focused on improving on where typical finite state machines fail, and that is its flexibility. I didn't want rigid states so I built a version of a state machine where the states are composed from action components, separating the responsibility of specific actions from the state to the components. This allows states to be much more flexible and encourages reusable code.

View on Itch.io: [https://pantheradigital.itch.io/godot-modular-character-controller](https://pantheradigital.itch.io/godot-modular-character-controller)

<a href="https://itch.io/embed-upload/17356390?color=4f6781" target="_blank">Play the demo now <span class="icon play-arrow"></span></a>
<details><summary><b>Controls</b></summary>

* WASD - move
* space - jump
* alt - dash (if obtained)
* tab - swap characters

_Third person character extended controls_
- shift - run
- double tap space - toggle between flying and walking
- q/e (while flying) - fly up/fly down
</details>

[tags: Godot, Game, Tool]


## [Fullstack Website](https://github.com/PantheraDigital/SNHURepo/tree/CS-465-Fullstack_Development_1)
![Screenshot of the landing page for a generic trip booking website.](https://raw.githubusercontent.com/PantheraDigital/InfoDump/refs/heads/main/project-imgs/PantheraDigital_FullstackClientMainPage.webp)

In this project I took a website template from HTML and CSS to the MEAN stack (MongoDB, Express.js, Angular.js, Node.js). In addition I used Handlebars, Postman, and DBeaver during development.

Other than taking the site to a client/server format, I also added an admin portal that allowed for registered users to login and make changes to the database, changing what was shown on the website.

[tags: Website, SchoolProject]


## [Cloud QA Website](https://github.com/PantheraDigital/SNHURepo/tree/CS-470-Full_Stack_Development_2)
![Diagram of cloud website services. Client connects to AWS, which connects to S3, which connects to API Gateway, which connects to Lambda, which connects to Dynamo DB.](https://raw.githubusercontent.com/PantheraDigital/InfoDump/refs/heads/main/project-imgs/PantheraDigital_AWSStack.webp)

In this project I took a website template that was using the MEAN stack, containerized it with Docker, then brought it to the cloud with AWS. The website is a QA site that allows users to post, edit, and remove questions and answers. The website is fully cloud based using AWS to allow the website to be significantly more scalable.

[tags: Website, SchoolProject]


## [Character Step](https://github.com/PantheraDigital/GodotCharacterStep)
![Screenshot of the github page for the Character Step project.](https://raw.githubusercontent.com/PantheraDigital/InfoDump/refs/heads/main/project-imgs/PantheraDigital_GodotCharacterStep.webp)

Code for moving objects across jagged surfaces. Performs collision detection and position manipulation to allow objects to "step" up and down from obstacles.

[tags: Godot, Game, Tool]


## [Tabletop Character Sheet Editor](https://pantheradigital.github.io/CharacterSheet/)
![Screenshot of the character sheet webpage, showing a form like layout with many text and number boxes.](https://raw.githubusercontent.com/PantheraDigital/InfoDump/refs/heads/main/project-imgs/PantheraDigital_CharaterStatSheet.webp)

Character sheet editor for D&D. Handles stat calculations for easier maintenance, organized spell and trait tracking with drag and drop elements, and quick spell adding from a spell database.

[tags: Website, D&D]


## [Enhanced Melee Trace](https://www.fab.com/listings/b3556c78-463b-4610-a81c-1bcb8916e202)
![Screenshot of Fab marketplace showing the listing for the Melee Hit Trace pack.](https://raw.githubusercontent.com/PantheraDigital/InfoDump/refs/heads/main/project-imgs/PantheraDigital_MeleeHitTrace.webp)

In this project I tackled a common problem in game development, collision detection for fast moving objects. The heart of the problem is that computers can only update programs so fast. Each update positions game objects and runs calculations. When an object has a velocity that covers more distance than the game can keep up with every physics update, that object will effectively teleport. This creates the possibility for missed collision, like a car traveling through a wall. To prevent this extra collision checks need to be made in the missed space so that physics can be corrected.

I also wrote a paper about the issue: [https://docs.google.com/document/d/1iHzTuZEroXdUIEyYPclzIXDA4Sg2yUvRwt1GIFtNd9I/edit?usp=sharing](https://docs.google.com/document/d/1iHzTuZEroXdUIEyYPclzIXDA4Sg2yUvRwt1GIFtNd9I/edit?usp=sharing)

[tags: UnrealEngine, Game, Tool]


## [EntityController2D](https://www.fab.com/listings/51702f7a-38f1-4718-938a-6c02227dae01)
![Screenshot of a video game character jumping between different green platforms.](https://raw.githubusercontent.com/PantheraDigital/InfoDump/refs/heads/main/project-imgs/PantheraDigital_EntityController.webp)

This was my first real attempt at a character controller, documentation, and a product for others. It's a pack that includes a state machine based character script, input handling, input remapping, and 2d physics handling for walking across various sloped grounds.

Originally this was just for me so that I could make some games, but I found it useful and believed it could help others, so I released it. I also updated it as I went on to make a few games using it.

You can also see the documentation webpage I made for it here: [https://pantheradigital.github.io/EntityControllerByPanthera/](https://pantheradigital.github.io/EntityControllerByPanthera/)

And a demo playable in browser here: [https://pantheradigital.itch.io/entity-controller-demo](https://pantheradigital.itch.io/entity-controller-demo)

[tags: Unity, Game, Tool]


## [DnD-WebScraper](https://github.com/PantheraDigital/DnD-WebScraper)
Python scripts that gather data from https://dnd5e.wikidot.com/ links. These are the scripts I use to make CSVs that are used in Google Sheets to act as a database for my Character Sheet project at https://pantheradigital.github.io/CharacterSheet/ 

[tags: WebScraper, D&D, Tool]


# Posts
## Attack Combos
How to implement data structures that allow you to make attack chains and input buffers. 
<hr>
![ComboHeader](https://raw.githubusercontent.com/PantheraDigital/InfoDump/refs/heads/main/post-imgs/ComboHeader.webp)
link: https://github.com/PantheraDigital/AttackCombos

[tags: CodeArchitecture, Game]


## Preventing Missed Collision In Games
What causes missed collisions in games?

When an object’s speed exceeds its own length in the direction it is moving, the colliders for that object can potentially skip over objects in the empty between space. This can happen to anything from melee weapons to projectiles.

<hr>
link: https://docs.google.com/document/d/1iHzTuZEroXdUIEyYPclzIXDA4Sg2yUvRwt1GIFtNd9I/edit?usp=sharing

[tags: CodeArchitecture, Game]

## FizzBuzz Challenge
**_FizzBuzz_** is a programming/division challenge where your program outputs _“Fizz”_ for integers divisible by 3, _“Buzz”_ for integers divisible 5, and _“FizzBuzz”_ for integers divisible by both 3 and 5.

Here I will show my solution in C# as well as another solution to an alternate version of the challenge that involves using a `List` for the results.

<hr>

#### FizzBuzz
Given a set of integers print _“Fizz”_ if an integer is divisible by 3, _“Buzz”_ if the integer is divisible by 5, _“FizzBuzz”_ if it is divisible by 3 and 5, and print only the integer if none of the conditions are true.

#### My Solution
```
static void FizzBuzz()
{
    for (int i = 1; i < 101; i++) // start with 1 to prevent dividing by 0
    {
        Console.WriteLine($"{i} - {((i % 3 == 0) ? "Fizz" : "")}{((i % 5 == 0) ? "Buzz" : "")}");
    }
};
```

Above is the solution I have come up with, apart from the loop it is a one line solution that creates a string based on the variable `i`. The modulus operator, `%`, is used to check for any remainder after dividing `i` by 3 and 5. Based on the result of each check the string _“Fizz”_ and/or _“Buzz”_ are added.

Although it is a one line solution it is not the most readable at first glance, this can be improved by separating out the ternary check.

```
static void FizzBuzz()
{
    for (int i = 1; i < 101; i++) // start with 1 to prevent dividing by 0
    {
        string fizz = (i % 3 == 0) ? "Fizz" : "";
        string buzz = (i % 5 == 0) ? "Buzz" : "";
        Console.WriteLine($"{i} - {fizz}{buzz}");
    }
};
```

The output of this solution will be a list of integers followed by _“Fizz”_, _“Buzz”_, _“FizzBuzz”_, or nothing depending on the index.

```
// Example output //
1 -
2 -
3 - Fizz
4 -
5 - Buzz
6 - Fizz
…
15 - FizzBuzz
```

#### Alternate Solution
Another version of this challenge involves storing the answers within a `List` where `i` is the index of each `List` element and the answer is stored as a `string`.

Here is a solution that utilizes a `List`:

```
static List<string> FizzBuzz(int n)
{
    List<string> result = new List<string>();

    for(int i = 1; i <= n; ++i)
    {
        if(i % 3 == 0 && i % 5 == 0)
        {
            result.Add("FizzBuzz");
        }
        else if (i % 3 == 0)
        {
            result.Add("Fizz");
        }
        else if (i % 5 == 0)
        {
            result.Add("Buzz");
        }
        else
        {
            result.Add(i.ToString());
        }
    }

    return result;
};
```

Now when the function is called it will return a `List` of results that is the length of argument `n` and in which each element is either its index in `string` form, _“Fizz”_, _“Buzz”_, or _“FizzBuzz”_.

[tags: CodeChallenge]
