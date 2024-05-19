## Lecture notes from the course
### Creating and starting a new React application
~~~bash
npx create-react-app my=app
cd my-app
export PORT=5100 && npm start
~~~
### React functional components
Create a function with argument, like `props` which holds key-value pairs of attributes of the JSX element of the component and their values.

Typed functional components in TypeScript:
~~~ts
export const MyComponent: React.FC<{
    name: string,
    description: string,
}> = (props) => { return (
    <p>{props.name}</p>
); }
~~~
### Useful hooks
#### `useState`
~~~js
const [todos, setTodos] = useState(initialTodos)
// ...
setTodos(todos => [...todos, newTodo])
~~~
### Noteworthy of TypeScript
Copiler options: `--noEmitOnError`, `--init` (creates a `tsconfig.json` file template).

Range `for` loop:
~~~ts
for (let car of cars) {
    console.log(car);
}
~~~
Class constructor is a method with name `constructor`.

Default access modifier is `private`

Special accessor syntax (works only with `tsc --target ES5`).
~~~ts
public get firstname(): string {
    return this._fiestname;
}
public set firstname(value: string) {
    this._firstname = firstname;
}
//...
myCustomer.firstname = "Susan";
~~~
Constructor properties to reduce code amount (defines and initialized properties at the same time):
~~~ts
constructor(private _firstname: string, private _lastname: string) { }
~~~
Class inheritance:
~~~ts
class Circle extends Shape {
    constructor(theX: number, theY: number, private _radius: numbner) {
        super(theX, theY);
    }

    getInfo(): string {
        return super.getInfo() + `, radius=${this._radius}`;    
    }
}
~~~
Abstract classes:
~~~ts
abstract class Shape {
    //
    abstract calculateArea(): nuber;
}
~~~
Interfaces
~~~ts
export interface Coach {
    getDailyWorkout(): string;
}

export GolfCoach implements Coach {
    getDailyWorkout(): string {
        return "...";
    }
}
~~~