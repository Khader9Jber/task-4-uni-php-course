# Task 4 university php course

What difference between Abstraction and Polymorphism

## Abstraction

> Abstraction definition...
>
> > means hiding the internal implementation for any functionality, and only showing the needed data which is useful for the user.
> >
> > > “shows” only essential attributes and “hides” unnecessary information
> > >
> > > > it can be implemented in the code in different ways, usually using abstract class and abstract function...

```php
<?php
abstract class AbstractClass
{
    abstract protected function prefixName($name);
}

class ConcreteClass extends AbstractClass
{

    public function prefixName($name, $separator = ".") {
        if ($name == "Superman") {
            $prefix = "Mr";
        } elseif ($name == "Superwoman") {
            $prefix = "Mrs";
        } else {
            $prefix = "";
        }
        return "{$prefix}{$separator} {$name}";
    }
}

$obj = new ConcreteClass;
echo $obj->prefixName("Superman"), "\n";
echo $obj->prefixName("Superwoman"), "\n";
?>
```

## Polymorphism

> Polymorphism definition...
>
> > Polymorphism describes a pattern in OOP in which multiple classes has varying functionality & implementation for these functions, but share common interface
> >
> > > which enables the developer to communicate with the objects of these classes in a uniform way via this interface of the parent class.
> > >
> > > > > each form will behave in different manner according to its implementation
> > > > >
> > > > > > e.g. You can deal with app shapes (Circle, Rectangle, Triangle,...), as one common form, it is the Shape form... because all of these are shapes in fact.

```php
<?php
class Shape {
    function draw(){}
}
############################################
class Circle extends Shape {
    function draw() {
     print "Circle has been drawn.</br>";
    }
}
############################################
class Triangle extends Shape {
    function draw() {
        print "Triangle has been drawn.</br>";
    }
}
############################################
class Ellipse extends Shape
{
    function draw() {
        print "Ellipse has been drawn.";
    }
}

$Val=array(2);

$Val[0]=new Circle();
$Val[1]=new Triangle();
$Val[2]=new Ellipse();

for($i=0;$i<3;$i++) {
    $Val[$i]->draw();
}
?>
```
