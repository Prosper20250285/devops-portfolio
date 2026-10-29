# Portfolio browser test plan

I run these browser checks from `test-logging.html` against the sibling
`index.html` portfolio. A navigation test passes when its link changes the URL
hash to the matching section and that section is visible. Link tests pass when
the expected destination (and, where specified, new-tab target) is present.
The image test requires every inline image to have alternative text and load.
TC-08 is an intentional negative test: this portfolio has no `#resume` section,
so it must be logged at ERROR level as a failure, and the final run summary
must still be written.

| Test ID | What is tested | Steps | Expected result |
|---|---|---|---|
| TC-01 | About navigation | Click **About** in the portfolio menu. | URL ends with `#about` and the About section is visible. |
| TC-02 | Collaboration navigation | Click **Collaboration** in the portfolio menu. | URL ends with `#collaboration` and the partnership section is visible. |
| TC-03 | Tasks Table navigation | Click **Tasks Table** in the portfolio menu. | URL ends with `#tasks` and the assignment tracker is visible. |
| TC-04 | Contact navigation | Click **Contact** in the portfolio menu. | URL ends with `#contact` and the contact section is visible. |
| TC-05 | Support email link | Click the support email link without opening an external mail application. | Link target is `mailto:sjitc2010@yahoo.fr`. |
| TC-06 | Institution website link | Click the institution website link with external navigation prevented. | Link target is `http://www.sjitc.ac.rw` and it specifies `_blank`. |
| TC-07 | Portfolio images and alt text | Inspect each inline image after the page loads. | All images have non-empty alternative text and loaded successfully. |
| TC-08 | Missing Resume section (negative) | Look for section `#resume`, which is not present in the portfolio. | The missing section is logged as an ERROR/FAIL with error and current URL; the runner continues and logs the final summary. |

## Run and save logs

Open `test-logging.html` in a browser. It loads `index.html` in the preview
below the controls. Select **Run portfolio tests** to execute all eight checks
and view the timestamped entries and summary. The intentional TC-08 failure
does not stop later logging. Select **Download log** and save the timestamped
`.txt` file in the repository's `logs/` folder. Each run has a different
filename so earlier evidence is not overwritten.
