# Using OpenGWAS API with R

## 1. Create an R Project
- Open RStudio (or R) and create a new project.

## 2. Install Required Packages
In R, install the necessary packages:

```r
# Install packages from the correct repositories
install.packages("TwoSampleMR", repos = c("https://mrcieu.r-universe.dev", "https://cloud.r-project.org"))
install.packages("ieugwasr")

# Load libraries
library(ieugwasr)
library(TwoSampleMR)
```
## 2. Generate an API Token
- Go to [OpenGWAS Profile](https://api.opengwas.io/profile/).
- Log in with your account.
- Click **Generate new token** and copy the token.

## 3. Save Token in `.Renviron`
- Open a text editor.
- Add the following line, replacing `<token>` with your actual token: `OPENGWAS_JWT=<token>`
- Save this file as **`.Renviron`** inside your R project directory.

## 4. Restart R Session
- Restart RStudio (or your R console) so the environment variable is loaded.

## 5. Verify Token Recognition
Run in R:

```r
ieugwasr::get_opengwas_jwt()
```
- If it returns a long random string, your token is recognised.
- If it returns `""`, then R did not load your `.Renviron`.

## 6.Test Token with API
Run in R:

```r
ieugwasr::user()
```
-If your token is valid, this will return a list of your user information.
-If it returns an error, the token is not working.
