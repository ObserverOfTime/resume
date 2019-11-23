# How to use this for your own resume

Feel free to submit an issue if you need help.

### Clone the repository

```sh
git clone https://github.com/ObserverOfTime/resume
cd resume
```

### Edit [`pug/_info.pug`](pug/_info.pug)

This file contains some basic info about you.

```js
- var phone = '' // your phone number
- var email = '' // your email address
- var homepage = '' // your homepage
- var github = '' // your GitHub username
- var linkedin = '' // your LinkedIn username
- var facebook = '' // your Facebook username
- var twitter = '' // your Twitter username
- var repo = '' // the link to this repo
```

If any of the above are blank, they will not be shown.

### Edit [`resume.scss`](resume.scss) *(optional)*

You can change any of these variables to alter the style of the resume.

|    Variable     |                         Description                          |
| :-------------: | :----------------------------------------------------------: |
| `$font-family`  | The font family used in the document. Pick one from [Google Fonts][fonts]. |
| `$font-subsets` |       The font's language subsets you wish to include.       |
|  `$page-size`   |    The size of the PDF page. See [MDN][size] for details.     |
|  `$page-width`  | The width of the page (in cm) that corresponds to `$page-size`. |
| `$page-height`  | The height of the page (in cm) that corresponds to `$page-size`. |
| `$page-margins` | The [margins][margin] of the page. Set this when printing the resume. |

[fonts]: https://fonts.google.com/
[size]: https://developer.mozilla.org/en-US/docs/Web/CSS/@page/size
[margin]: https://developer.mozilla.org/en-US/docs/Web/CSS/margin

### Edit the [`locale`](locale) files

These files contain translatable strings.
You can remove or add your own languages
but you may have to edit [`package.json`](package.json) and
[`.github/workflows/build.yml`](.github/workflows/build.yml) accordingly.

|              Key              |                         Description                          |
| :---------------------------: | :----------------------------------------------------------: |
|            `name`             |                          Your name.                          |
|             `bio`             |                         A short bio.                         |
|          `location`           |                        Your location.                        |
|         `experiences`         | An object containing your experiences.<br>Delete it if you don't want them shown. |
|      `experiences.title`      | The title of the `experiences` section.<br>Normally, you don't need to change this. |
|      `experiences.list`       |                 A list of your experiences.                  |
|   `experiences.list.*.name`   |                 The name of this experience.                 |
| `experiences.list.*.details`  |             Some details about this experience.              |
|          `projects`           | An object containing your projects.<br>Delete it if you don't want them shown. |
|       `projects.title`        | The title of the `projects` section.<br>Normally, you don't need to change this. |
|        `projects.list`        |               A list of your notable projects.               |
|    `projects.list.*.name`     |                  The name of this project.                   |
|     `projects.list.*.url`     |                   The URL of this project.                   |
|   `projects.list.*.details`   |               Some details about this project.               |
|        `achievements`         | An object containing your achievements.<br>Delete it if you don't want them shown. |
|     `achievements.title`      | The title of the `achievements` section.<br>Normally, you don't need to change this. |
|      `achievements.list`      |                 A list of your achievements.                 |
|  `achievements.list.*.name`   |                The name of this achievement.                 |
| `achievements.list.*.details` |             Some details about this achievement.             |
|          `education`          | An object containing your education.<br>Delete it if you don't it shown. |
|       `education.title`       | The title of the `education` section.<br>Normally, you don't need to change this. |
|       `education.list`        |            A list of your educational endeavours.            |
|    `education.list.*.name`    |           The name of the school/university/etc..            |
|  `education.list.*.details`   |             Some details, including the degree.              |
|           `skills`            | An object containing your skills.<br>Delete it if you don't want them shown. |
|        `skills.title`         |              The title of the `skills` section.              |
|         `skills.list`         |                    A list of your skills.                    |
|          `passions`           | An object containing your passions<br>Delete it if you don't want them shown. |
|       `passions.title`        |             The title of the `passions` section.             |
|        `passions.list`        |                   A list of your passions.                   |
|          `languages`          | An object containing your (natural) languages.<br>Delete it if you don't want them shown. |
|       `languages.title`       |            The title of the `languages` section.             |
|       `languages.list`        |              A list of the languages you know.               |
|    `languages.list.*.name`    |                  The name of this language.                  |
|  `languages.list.*.details`   |       Some details about this language (e.g. degrees).       |

### Build the resume

*Skip to the [next step](#change-repository-links) if you'd rather let GitHub build it.*

```sh
# you can use yarn instead of npm
npm install # install the dependencies
npm run build-EN # build the English resume
npm run build-GR # build the Greek resume
```

You should now have the English resume in `build/Resume-EN.pdf`
and the Greek resume in `build/Resume-GR.pdf`.

---

*The following steps are not required if you're only running this locally.*

### Change repository links

[`README.md`](README.md) and [`package.json`](package.json) link to this repository.
Change these links to your own.

|      File      |      Link      |
| :------------: | :------------: |
|  `README.md`   |   `[en_GB]`    |
|  `README.md`   |     `[gr]`     |
| `package.json` |    `"name"`    |
| `package.json` | `"repository"` |

### Update version

You should update the version in [`package.json`](package.json) every time you push to `master`.

Otherwise, the automated release action may fail.
