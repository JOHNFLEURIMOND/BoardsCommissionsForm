
![Old Boards and Commissions Application Form](img/bg.png)

![New Boards and Commissions Application Form](img/BC.png)

# My Awesome Project
After graduating my bootcamp with Resilient Coders, I landed a internship engineering for the City of Boston Digital Team and their goal in this application was to bring the existing cityofboston.gov boards and commissions webpage (HTML, CSS, and Javascript) onto boston.gov(React.js, Next.js). My task in this project was to improve the existing functionality and user experience for the applications form.



## How It's Made ## Lessons Learned:
React.js, Typescript, Next.js, Formik, Storybook, GraphQL, Jest, Percy framework of choice Under the Hood:First starting off with the Typescript that I used with React. Typescript is a strict syntactical superset of JavaScript that has its own linter called TS Lint and is also designed to compile to JavaScript. Typescript An App.tsx is the file template that I had to used for my components.


 My mentor said it best in their last medium article... "I had thrown John into a type-checking world without preparation. He fell victim to a paradox of guard rails: it can take more effort to deal with a checker’s “helpful” error messages than it would ever be to debug the problems it’s warning you against." (https://medium.com/innovation-and-technology/deciphering-typescripts-react-errors-8704cc9ef402)

 TypeScript was giving me messages saying "Type '{ name: string; placeholder: string; value: string; onChange: (e: ChangeEvent<any>) => void; erro...' is not assignable to type 'IntrinsicAttributes & IntrinsicClassAttributes<FormWithElement> & Readonly<{ children?: ReactNode...'. Type '{ name: string; placeholder: string; value: string; onChange: (e: ChangeEvent<any>) => void; erro...' is not assignable to type 'Readonly<Props>'. Property 'title' is missing in type '{ name: string; placeholder: string; value: string; onChange: (e: ChangeEvent<any>) => void; erro...'

 ....I was lost but I learned from my mentor that I had to first understand what the error trying to tell me and for this matter its saying Property 'title' is missing in type '{ name: string; placeholder: string; value: string;"" Because I had passed several props into a interface and title being one of them TypeScript picked that up and thru that error to make me aware that it should be.

  I am using a NPM package called Formik. Formik is a less painful way of making forms with event callback functions like (handleBlur, handleSubmit), setup validation, and easy error handling.. In regular React code, lets say you have to make a input, I would have to use two-way data binding. if you want to use change/call back handler, you would have to use this.setState for your change/call back handler and where you would like to target exactly for the state to change and pass it to the input and every input after that. Which becomes redundant having to setState and binding for things like handleChange, handleSubmit, handleBlur and other handlers, but Formik has some of these and does all the heavy lifting.

  Being a high order component, you pass it a configuration and it injects property in your form. It tracks all fields that have been visited, what the form’s values are, and much more. Also, they all have the same key to handle the primitives unlike regular React code. The states are initialized by actually writing the callbacks like handleSubmit in the actual Formik code instead of writing it about the render( ) like in regular React. As shown in the code below. you would write something like this….

  `class Application extends Component {
  componentWillMount = () => {
    this.selectedCheckboxes = new Set();
  }

  toggleCheckbox = label => {
    if (this.selectedCheckboxes.has(label)) {
      this.selectedCheckboxes.delete(label);
    } else {
      this.selectedCheckboxes.add(label);
    }
  }

 handleFormSubmit = formSubmitEvent => {
   formSubmitEvent.preventDefault();

   for (const checkbox of this.selectedCheckboxes) {
     console.log(checkbox, 'is selected.');
   }
 }`
     ...but in Formik the only thing you would have to do is use a deconstructed function and add the functions like handleBlur, handleChange, and handleSubmit to pass to through certain properties. You don’t have to change the code just write the type compatible with the property.

                 <TextInput
                     title="First Name"
                     name="firstName"
                     placeholder="First Name"
                     value={values.firstName}
                     onChange={handleChange}
                     error={touched.firstName && errors.firstName}
                     onBlur={handleBlur}
                   />

  They even have cool props called errors and touched and used correctly when set up. If a field is visited (touched) when you set up your Yup validation, Yup validation is a object schema validation, when it is blurred it will display the error you created. Here is an example of the code:

firstName: Yup.string()
               .required('Your First Name Is Required!')
               .min(2, 'Your First Name Needs To Be Valid’),

With firstName being the initialValue passed thru to Formik from my higher order component I created. It now knows that that TextInput.tsx is a text input field that is named “firstName” and it is a string that is required and has a minimal of 2 characters, if the field is touched ( error={touched.firstName && errors.firstName} )  then blurred ( {handleBlur} ) it will display the message created in the .min function. Or let’s say the touch and let’s say there was no onChange it will let you know that it is required as well.
 Just like with anything you do in React you will first start off with an "import React from 'react’;” as well as Formik, import { Formik } from 'formik’;
       Once Formik is imported, for this app I had to create a better user experience by making a new component instance for the text inputs of the form as well as validation (Formik uses Yup for object schema validation. This being my first major React project I had grasped of the gist of Formik and what it needed to work.
 First, I had to pass the props to Formik in the TextInput.tsx. I thought it was simple as exporting extensions React.Component<Props> , but I also forgot I need to list the export interface so Formik knew the values of the props. This was the tough part because I didn’t understand the errors I was receiving like “this isn’t a property for this type” and making sure all the props were lined up across the board.






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
