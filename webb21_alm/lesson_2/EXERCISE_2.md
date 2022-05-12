# Exercise 2

## Instructions

### `Exercise - YAML - Person`

In this exercise we will learn how to write YAML. Yaml is needed when you create a GitLab pipeline.

We will use `yaml-schema-validator` globally installed with npm, so that we can learn YAML by doing.

```bash
# install schema command
npm install -g yaml-schema-validator

# test the command with
schema --version
```

if you have a file `person.yml`

```yaml
---
person:
  name:
    first_name: robert
```

```bash
# The result when running
schema validate -f person.yml --schema lesson_2/schemas/schema_person.yml

# ERROR : ====== Schema Validation Error ======
# ERROR : 5 mismatches and 0 warnings found.
# 1. person.name.last_name is required.
# 2. person.age is required.
# 3. person.class is required.
# 4. person.start_year is required.
# 5. person.hobbies.0 is required.
```

- Complete the person.yml file so it passes the schema validation without errors.

### `Exercise - YAML - Schedule`

if you have a file `schedule.yml`

```yaml
---
schedule:
    year: 22
```

```bash
# The result when running
schema validate -f schedule.yml --schema lesson_2/schemas/schema_schedule.yml

# ERROR : ====== Schema Validation Error ======
# ERROR : 2 mismatches and 0 warnings found.
# 1. schedule.year must be of type String.
# 2. schedule.program is required.
```

- Complete the schedule.yml file so it passes the schema validation without errors.

### `Exercise - GitLab`

In this exercise we will write our first pipeline with YAML. For this exercise we will create a blank project [GitLab blank project](https://gitlab.com/projects/new#blank_project)

1. Clone your new blank project, named My First Pipeline
2. Add the schemas folder from `lesson_2` to your new projects git repository, you can clone to your local machine or use the upload feature in gitlab.
3. Go to GitLab and add a `.gitlab-ci.yml`
4. Edit `.gitlab-ci.yml` with vscode or code directly in GitLab `Pipeline Editor`
5. Set the default image to node:lts-alpine

   ```yaml
    default:
      image: node:lts-alpine
   ```

6. Create a job in your yaml file

    ```yaml
    my_job:
      before_script:
          - echo "this is before script"

      script:
          - echo "This is the script step"
    ```

7. In `before script` install `yaml-schema-validator`

    ```yaml
    npm install -g yaml-schema-validator
    ```

8. Test your installation in `script`

    ```yaml
    script:
          - echo "This is the script step"
          - schema --version
    ```

9. Add your YAML file from previous exercise and make sure it validate successfully. i.e if you add it as person.yml, add this to `gitlab-ci.yml`

    ```yaml
    script:
      - cat person.yml
      - schema validate -f person.yml -s schemas/schema_person.yml | grep -q 'SUCCESS'
    ```

10. Create a new job for each of car.yml and computer.yml, your pipeline should fail when it tries to validate car.yml and computer.yml
11. Take a screenshot of the failing pipeline
12. Make sure to clone your project to your local machine (if not done in previous steps).
13. Add the missing data for car.yml and verify that the job will pass successfully
14. Add the missing data for computer.yml and verify that the the job and the whole pipeline passes successfully
15. Take a screenshot of the successful pipeline

## Hand in instructions

In repository [webb21_alm](https://gitlab.com/robert-alfwar/webb21_alm)

- Create a branch with name `USERNAME_lesson_2`
- Submit the failing and successful pipeline screenshot

Submit screenshot[s] and/or file[s] in a `Merge Request`

- Remember to assign the pull request to the teacher.
- You can use the `attach a file` for screenshots
