# CDK Examples

This project uses Git submodules. Below are instructions on how to work with submodules in this repository.

## Setting up Git Submodules

1. Clone the main repository:
   ```
   git clone https://github.com/andrewlohc/cdk-examples.git
   cd cdk-examples
   ```

2. Initialize the submodules:
   ```
   git submodule init
   ```

3. Update the submodules:
   ```
   git submodule update
   ```

Alternatively, you can clone the repository and initialize submodules in one step:
```
git clone --recursive https://github.com/andrewlohc/cdk-examples.git
```

## Making Changes to Submodules

1. Navigate to the submodule directory:
   ```
   cd path/to/submodule
   ```

2. Ensure you're on the desired branch:
   ```
   git checkout main
   ```

3. Make your changes, commit, and push:
   ```
   git add .
   git commit -m "Your commit message"
   git push origin main
   ```

4. Return to the main repository root:
   ```
   cd ../..
   ```

5. Update the main repository to point to the new submodule commit:
   ```
   git add path/to/submodule
   git commit -m "Update submodule to latest commit"
   git push origin main
   ```

## Updating Submodules

To update all submodules to their latest commits:

1. Pull the latest changes from the main repository:
   ```
   git pull origin main
   ```

2. Update all submodules:
   ```
   git submodule update --remote --merge
   ```

3. Commit the changes in the main repository:
   ```
   git add .
   git commit -m "Update submodules to latest"
   git push origin main
   ```

## Adding a New Submodule

To add a new submodule to the project:

1. Add the submodule:
   ```
   git submodule add https://github.com/andrewlohc/cdk-examples.git path/to/submodule
   ```

2. Commit the changes:
   ```
   git add .
   git commit -m "Add new submodule"
   git push origin main
   ```

## Removing a Submodule

1. Remove the submodule entry from `.git/config`:
   ```
   git submodule deinit -f path/to/submodule
   ```

2. Remove the submodule from the working tree and .gitmodules:
   ```
   git rm -f path/to/submodule
   ```

3. Remove the submodule directory from .git/modules:
   ```
   rm -rf .git/modules/path/to/submodule
   ```

4. Commit the changes:
   ```
   git add .
   git commit -m "Remove submodule"
   git push origin main
   ```

Remember to replace `path/to/submodule` with the actual path where you want to add the submodule in your project structure.
