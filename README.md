## MEM Power automate Repo
This repo is intended as the source history for changes/updates to the PAD flows. Editing the flow itself needs to be done on the PAD app and must be in a solution so that it can be exported via the `pac` cli command and then push to git.

# Solutions
Solutions are saved in the /solutions directory.

# Commands to use for pushing solution changes to the repo
NOTE: Requires the PAC ClI installed

1. Authenticate
`pac auth create`

2. List Environment
`pac env list`

3. Select Environment
`pac env select --environment <environment-id>`

4. Export Solution

pac solution export `
   --name "SolutionName" `
   --path SolutionName.zip `
   --managed false

5. Unpack Solution
pac solution unpack `
   --zipfile V10Solution.zip `
   --folder ./solutions/V10 `
   --packagetype Both


Where, `--packagetype` can be Managed, Unmanaged or Both

6. Push to git using `git push` command.


## Worfklow

Export Solution -> Overwrite SolutionName.zip -> pac solution unpack -> git add . -> git commit -> git push