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
