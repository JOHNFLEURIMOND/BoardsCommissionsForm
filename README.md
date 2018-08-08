
![Old Boards and Commissions Application Form](img/bc.png)

![New Boards and Commissions Application Form](img/BC.png)

# My Awesome Project
After graduating my bootcamp with Resilient Coders, I landed a internship engineering for the City of Boston Digital Team and their goal in this application was to bring the existing cityofboston.gov boards and commissions webpage (HTML, CSS, and Javascript) onto boston.gov(React.js, Next.js). My task in this project was to improve the existing functionality and user experience for the applications form.



## How It's Made ## Lessons Learned:
React.js, Typescript, Next.js, Formik, Storybook, GraphQL, Jest, Percy framework of choice Under the Hood:First starting off with the Typescript that I used with React. Typescript is a strict syntactical superset of JavaScript that has its own linter called TS Lint and is also designed to compile to JavaScript. Typescript An App.tsx is the file template that I had to used for my components.


 My mentor said it best in their last medium article... "I had thrown John into a type-checking world without preparation. He fell victim to a paradox of guard rails: it can take more effort to deal with a checker’s “helpful” error messages than it would ever be to debug the problems it’s warning you against." (https://medium.com/innovation-and-technology/deciphering-typescripts-react-errors-8704cc9ef402)

 TypeScript was giving me messages saying "Type '{ name: string; placeholder: string; value: string; onChange: (e: ChangeEvent<any>) => void; erro...' is not assignable to type 'IntrinsicAttributes & IntrinsicClassAttributes<FormWithElement> & Readonly<{ children?: ReactNode...'. Type '{ name: string; placeholder: string; value: string; onChange: (e: ChangeEvent<any>) => void; erro...' is not assignable to type 'Readonly<Props>'. Property 'title' is missing in type '{ name: string; placeholder: string; value: string; onChange: (e: ChangeEvent<any>) => void; erro...'

 ....I was lost but I learned from my mentor that I had to first understand what the error trying to tell me and for this matter its saying Property 'title' is missing in type '{ name: string; placeholder: string; value: string;"" Because I had passed several props into a interface and title being one of them TypeScript picked that up and thru that error to make me aware that it should be.

React.js and Formik.....


## Optimizations
I have to finish this Read.me

## portfolio:

**WEBSITE:** https:/johnfleurimond.com



## Installation

1. Clone repo
2. run `yarn install`

## Usage

1. run `yarn dev`
2. Navigate to `localhost:3000/commissions/apply`
