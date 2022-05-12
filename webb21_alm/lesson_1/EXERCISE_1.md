# Exercise 1

## Instructions part 1

The main goal of exercises part 1 is to learn how to hand in a exercise. We will verify that git, docker and nodejs works properly on your environment. You will also learn how to use markdown, a lightweight markup language commonly used in i.e GitHub, GitLab, but also for docs and generating frontend.

### `Exercise - git`

```bash
git --version 
```

### `Exercise - docker`

```bash
docker version
```

### `Exercise - Node.js`

```bash
node --version
```

### `Exercise - markdown`

Create a markdown file with headings, a list, a javascript code block and a link. You can install the Visual Studio Code extension if you want the markdown preview functionality.

- Take a screenshot of a `rendered` markdown file, using gitlab, vscode or any other tool.

## Hand in instructions for part 1 - Git, Docker, Node.js and markdown

In repository [webb21_alm](https://gitlab.com/robert-alfwar/webb21_alm)

- Create a branch with name `USERNAME_lesson_1`
- Create a folder in the root named `USERNAME`
- Create a file `USERNAME.md` in that folder

Submit screenshot[s] and file[s] in a `Merge Request`

- Remember to assign the pull request to the teacher.
- You can use the `attach a file` for screenshots

<div class="page"/>

## Part 2

In Part 2 we will work with GitLab and git.

### `Group Exercise - GitLab` 3 persons

1. One person in the team Creates a new GitLab Project named `webb21_food`
2. Add your team members as `Developers` in Project Information -> Members -> Invite Members

- Everyone should work in personal branches, forcing you to merge the work in each iteration.
- After each iteration, create a new branch from main
- Everyone should work in a file called food.md

#### The Recipe

All changes are made in branches and merged with a merge request after each iteration.

##### Iteration 0

1. Person 1 (owning the repository) - Clone the repository to your local machine
2. Person 1 share your screen and adds a file named food.md.

    ```text
    # Food.md
    
    ## list of ingredients

    ## Description

    ```

3. Person 1 (owning the repository),

    ```bash
    git add food.md
    git commit -m "Initial commit of food.md"
    git push
    ```

4. Inspect the file is visible for all team members in GitLab
5. All team members clone the repository to your local machine
6. Prepare a branch for iteration 1
   1. git pull (to make sure you have the latest changes)
   2. git status (make sure you are on main branch)
   3. git branch YOUR_USERNAME_iteration_1
   4. git switch YOUR_USERNAME_iteration_1
   5. git status (make sure you are on YOUR_USERNAME_iteration_1)

##### Iteration 1

- Person 1 is responsible for adding ingredients to a list in food.md
- Person 2 should write a description of how the cook the recipe in food.md
- Person 3 now modify for how much of each ingredient, both in the list and in the descriptive text in food.md

##### Iteration 2

Merge the work from each persons branch to main. Make sure to do a git pull between each successful merge to main.

- Person 1 again add new ingredients, forcing the others to adapt.

##### Iteration 3

Merge the work from each persons branch to main. Make sure to do a git pull between each successful merge to main.

- Person 1 changes a ingredient, forcing the others to adapt.

### `Exercise - GitLab`

Learn how to manually create a merge conflict and solve it in the terminal. Read the instructions carefully.

- GitLab training [merge conflict](https://docs.gitlab.com/ee/university/training/topics/merge_conflicts.html)

### `Extra Exercise - GitHub`

Learn how to use solve merge conflicts in GitHub, also you see an example of a Pull Request bot assisting you.

- GitHub training [merge conflict](https://lab.github.com/githubtraining/managing-merge-conflicts)

## Hand in instructions

No hand in for this exercise.
