# Zafor's Portfolio  [![License: MIT](https://img.shields.io/badge/license-MIT-blue)](LICENSE.md)

## Personal developer portfolio for Zafor

Built with React, driven entirely by JSON content files under `public/profile/`, with light/dark theme support.

## Features

⚡️ Modern UI Design + Reveal Animations\
⚡️ Made with React\
⚡️ Fully Responsive\
⚡️ Content-driven — edit JSON, not code\
⚡️ Light/Dark theme support

---

## Getting Started 🚀

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites 📋

You'll need [Git](https://git-scm.com) and [Node.js](https://nodejs.org/en/download/) 24.x (which comes with [NPM](http://npmjs.com)) installed on your computer.

## Setup 🔧

From your command line, first clone the repository:

```bash
# Clone the repository
$ git clone https://github.com/ZaforAbdullah/portfolio.git

# Move into the repository
$ cd portfolio
```

Then install dependencies and start the dev server. `legacy-peer-deps` is already enabled via `.npmrc`, so a plain install works.

```bash
# Install dependencies
$ npm install

# Start the development server
$ npm start
```

Once your server has started, go to this url `http://localhost:3000/` to see the portfolio locally.
The page will reload if you make edits.

---

## Customization Instructions:

### Step 1 - DATA & IMAGES

All customizable files are inside the `public/` folder, organised mainly into `public/images/` and `public/profile/`.
- `public/images` contains all the image assets that can be customized on website
- `public/profile` contains all text and info inside json files that can be customized according to need

### (1) NavBar

- Open `public/profile/navbar.json` 
It has 2 keys, *logo* and *sections*.

```
{
    "logo" : {
        "source": "images/logo.png",
        "height" : 45,
        "width" : 50
    },
    "sections": [
        {
            "title": "Home",
            "href": "/"
        },
        {
            "title": "About",
            "href": "/about"
        },
        {
            "title": "Skills",
            "href": "/skills"
        },
        {
            "title": "Education",
            "href": "/education"
        },
        {
            "title": "Experience",
            "href": "/experience"
        },
        {
            "title": "Projects",
            "href": "/projects"
        }
    ]
}
```

| key | Description |
| ----------- | ----------- |
| logo | image you want to show as brand image on NavBar. It can be also be a simple logo with just your intitials|
| logo.source | path to the logo image |
| logo.height | height of logo |
| logo.width | width of logo |
| sections | array of sections that you want to show on Navbar as links | 
| sections.title | title of the section | 
| sections.href | link to that section. Same as *path* mentioned in `routes.json` | 
| sections.type | Opens in a new tab if value is *link*. `optional` field | 

### (2) Routes
- open `public/profile/routes.json`

```
{
    "sections": [
        {
            "component": "About",
            "path": "/about",
            "headerTitle": "About"
        },
        {
            "component": "Skills",
            "path": "/skills",
            "headerTitle": "Skills"
        },
        {
            "component": "Education",
            "path": "/education",
            "headerTitle": "Education"
        },
        {
            "component": "Experience",
            "path": "/experience",
            "headerTitle": "Experience"
        },
        {
            "component": "Projects",
            "path": "/projects",
            "headerTitle": "Projects"
        }
    ]
}
```

| key | Description |
| ----------- | ----------- |
| sections | array of sections that you want to create route for | 
| sections.component | name of the Component. No need to change it unless you want to customize the entire Component. | 
| sections.path | route for the particular section. this is the path where the particular section will be accessible | 
| sections.headerTitle | title to be shown on the top of that section page | 

- For component customization, create a component of your own inside `src/components/` and use name of that component here.

### (3) Home Section

#### Home Info
- open `public/profile/home.json`

```
{
    "name": "Your Name",
    "roles": ["a Developer", "a Freelancer"]
}
```

| key | Description |
| ----------- | ----------- |
| name | your name | 
| roles | string array separated by `,`. mention your roles here | 

#### Social Links
- open `public/profile/social.json`

```
{
    "social": [
        {
            "network" : "linkedin",
            "href": "https://linkedin.com/"
        },
        {
            "network" : "github",
            "href": "https://github.com/"
        },
        {
            "network" : "email",
            "href": "mailto:test@test.com"
        }
    ]
}
```

| key | Description |
| ----------- | ----------- |
| social | array of social links | 
| social.network | network name as provided in [react-social-icons](https://jaketrent.github.io/react-social-icons/) |
| social.href | link for particular social network |

- we are using [react-social-icons](https://jaketrent.github.io/react-social-icons/) here. you can visit it to see all available social icons to use

### (4) About Section

- open `public/profile/about.json`

```
{
    "about": " This is where you can describe about **yourself**.",
    "imageSource": "images/about/profile.png"
    
}
```

| key | Description |
| ----------- | ----------- |
| about | write about yourself, your works and goals here. `markdown` supported | 
| imageSource | path to your profile image. (recommended size 400 x 450) |

### (5) Skills Section

- open `public/profile/skills.json`

```
{
    "intro": "I love building things that matter — from performant frontends to production AI systems.",
    "skills": [
        {
            "title": "Languages",
            "items" : [
                {
                    "icon": "images/skills/ts.png",
                    "title": "TypeScript"
                },
                {
                    "icon": "images/skills/js.png",
                    "title": "JavaScript"
                }
            ]
        },
        {
            "title": "Frontend",
            "items" : [
                {
                    "icon": "images/skills/react.png",
                    "title": "React.js"
                }
            ]
        },
        {
            "title" : "Cloud & DevOps",
            "items": [
                {
                    "icon": "images/skills/git.png",
                    "title": "Git"
                }
            ]
        }
    ]
}
```

| key | Description |
| ----------- | ----------- |
| intro | small introduction line related to your skills. `markdown` supported | 
| skills | array containing skills under different categories |
| skills.title | title for category under which you want to list particular skills |
| skills.items | array containing skills for this category |
| skills.items.icon | path to skill logo |
| skills.items.title | title of skill |

- many pre existing skill logos are available inside `public/images/skills`.

### (6) Education Section

- open `public/profile/education.json`

```
{
    "education":[
        {
            "title": "Jun 20XX - Jun 20YY",
            "cardTitle": "B.Tech, Computer Science",
            "cardSubtitle":"XYZ University, City",
            "cardDetailedText": "CGPA - 9.5",
            "icon" : {
                "src": "images/education/lorem-ipsum.png"
            }
        },
        {
            "title": "Apr 20XX",
            "cardTitle": "High School",
            "cardSubtitle":"ABC School, City",
            "cardDetailedText": "Marks - 95%"
        }
    ]
}
```

| key | Description |
| ----------- | ----------- |
| education | array containing education history of a person | 
| education.title | date range during which this education was pursued or passing date |
| education.cardTitle | degree or course name |
| education.cardSubtitle | school or institute name |
| education.cardDetailedText | extra info such as marks or cgpa |
| education.icon | icon shown on the timeline. `optional` field|
| education.icon.src | path to icon |

### (7) Experience Section

- open `public/profile/experiences.json`

```
{
    "experiences": [
        {
            "title": "Software Engineer",
            "subtitle": "XYZ Ltd",
            "workType": "Full-time",
            "workDescription": [
                "Integrated **2** new product.",
                "Worked on adding **def** to **bcd**. Improved speed by 50%."
            ],
            "dateText": "06/20XX – Present"
        },
        {
            "title": "Software Engineer",
            "subtitle": "XYZ Ltd",
            "workType": "Internship",
            "workDescription": [
                "Worked on abc."
            ],
            "dateText": "01/20XX – 05/20XX"
        },
        {
            "title": "App Developer",
            "subtitle": "ABC Pvt Ltd",
            "workType": "Freelance",
            "workDescription": [
                "Developed the official apps for the startup for both Android and iOS using hybrid framework.",
                "Done bcd work."
            ],
            "dateText": "09/20XX – 01/20YY"
        }
    ]
}
```

| key | Description |
| ----------- | ----------- |
| experiences | array containing work experiences of a person | 
| experiences.title | role or designation title |
| experiences.subtitle | company or organization name. `optional` field |
| experiences.workType | type of work experience. example - internship, freelance, full-time. `optional` field |
| experiences.workDescription | string array to highlight specific points related to that work experiece. `markdown` supported |
| experiences.dateText | date range text during which particular work experience was pursued. |

### (8) Projects Section

- open `public/profile/projects.json`

```
{
    "projects" : [
        {
            "image" : "images/projects/kanban-poster.png",
            "title": "Kanban Board",
            "bodyText": "- A **drag-and-drop** Kanban board for task management built with **React** and **TypeScript**.\n - State management with **Zustand**; smooth animations with Framer Motion.",
            "links": [
                {
                    "text": "GitHub",
                    "href": "https://github.com/ZaforAbdullah/Kanban-Board"
                },
                {
                    "text": "Live",
                    "href": "https://nextjs-kanban-board-project.vercel.app/"
                }
            ],
            "tags" : [
                "React",
                "TypeScript",
                "Zustand",
                "Framer Motion"
            ]
        }
    ]
}
```


| key | Description |
| ----------- | ----------- |
| projects | array containing projects information |
| projects.image | add project poster here. `optional` field. |
| projects.title | title of the project |
| projects.bodyText | description of project. `markdown` supported |
| projects.links | clickable links related to the project. `optional` field |
| projects.links.text | title of link to display |
| projects.links.href | actual link to be redirected to on click of the button |
| projects.tags | string array containing tags related to projects. `optional` field | 


### Step 2 - STYLES

Change the color theme of the website -

Go to `/src/theme/themes.js` and change the values of the required components both under lightTheme and darkTheme with your prefered HEX color.


```theme
//Default Values
export const lightTheme = {
  background: '#fff',
  color: '#121212',
  accentColor: '#3D84C6',
  chronoTheme: {
    cardBgColor: 'white',
    cardForeColor: 'black',
    titleColor: 'white',
  },
  timelineLineColor: '#ccc',
  cardBackground: '#fff',
  cardFooterBackground: '#f7f7f7',
  cardBorderColor: '#00000020',
  navbarTheme: {
    linkColor: '#dedede',
    linkHoverColor: '#fefefe',
    linkActiveColor: '#fefefe',
  },
  bsPrimaryVariant: 'light',
  bsSecondaryVariant: 'dark',
  socialIconBgColor: '#121212',
};

export const darkTheme = {
  background: '#121212',
  color: '#eee',
  accentColor: '#3D84C6',
  chronoTheme: {
    cardBgColor: '#1B1B1B',
    cardForeColor: '#eee',
    titleColor: 'black',
  },
  timelineLineColor: '#444',
  cardBackground: '#060606',
  cardFooterBackground: '#181818',
  cardBorderColor: '#ffffff20',
  navbarTheme: {
    linkColor: '#dedede',
    linkHoverColor: '#fefefe',
    linkActiveColor: '#fefefe',
  },
  bsPrimaryVariant: 'dark',
  bsSecondaryVariant: 'light',
  socialIconBgColor: '#fefefe',
};

```

### Step 3 - EXTRA

Go to `public/index.html`. Change *title* and *logo* if you want to customize it.

---

## Deployment 📦

Once you finish your setup, deploy the site with [Vercel](https://vercel.com) — it's the easiest option for a React app like this.

## Author

- **Zafor A.** - [github.com/ZaforAbdullah](https://github.com/ZaforAbdullah)

## Credits

Originally based on the [dev-portfolio](https://github.com/mayankagarwal09/dev-portfolio) template by [Mayank Agarwal](https://github.com/mayankagarwal09), since customized for personal use.

## License 📄

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

