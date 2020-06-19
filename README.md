# Replace-Conditional-with-Polymorphism


● just to talk about refactoring of code 

● If we have a class full of Male & female students ,they went to pee we want to present that in a code.
  it will be something like that.

## Example using switch case:

```
class Human {
  // ...
  String goPee() {
    switch (Pee) {
      case Male:
        return "Stand Up";
      case Female:
        return "Sit Down";
    }
  }
}
```

● To refoctor this code correctly think of it like we have more than ONE if condition, In real life applications use  
     more than 8 conditions, I have seen this before. 

● It was very hard to understand every if condition.

● To reduce the code & make it maintianble, we could refactor it.

## First create abstract class called human

```
abstract class Human {
  // ...
  abstract String goPee();
}
```

In this abstract method when you want to use it, you must inherate it from class Human then use it, like that 

## Create class for Male

```
public class Male extends Human{
...
    @Override
    public String goPee(){
        return ("Stand Up");
    }
}
```
## class for Female 

```
public class Female extends Human{
    @Override
    public void goPee(){
        System.out.println("Sit Down");
    }
}
```

To check it for all the classroom 

## Main Method

```
public static void main(String[] args){
    ArrayList<Human> group = new ArrayList<Human>();
    group.add(new Male());
    group.add(new Female());
    // ... add more...

    // tell the class to take a pee break
    for (Human person : group) person.goPee();
}

```

Please if someone wants to modify it, very welecome.

