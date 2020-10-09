# Design Pattern - Factory Pattern

fonte:  https://www.tutorialspoint.com/design_pattern/factory_pattern.htm

## Resumo - factory Pattern

**É um padrão-tipo de criação. Uma das melhores para criação de um objeto.**

	
	1. criar a public interface com as métodos abstract e constantes.
	2. criar as classes concretas que implementam a interface e que @override
	   os métodos da interface executando o que deseja.
	3. criar a classe factory que declarará os métodos de criação dos objetos-interface conforme os vários tipos.
	4. a classe principal instanciará objetos da classe factory e pelo métodos declarados criará o objeto-tipo da
           classe concreta desejada que implementa a interface.
	5. e por meio do objeto-tipo da classe concreta criada realizar o método desejado.
	   
	obs.: Como interface, TODOS os membros são públicos de forma implícita e NÃO PODEM especificar nenhum detalhe
	de implementação tais como declarações de métodos concretos e variáveis de instãncia. Todos os métodos
	declarados em uma interface são implicitamente métodos public abstract e todos os campos são implicitamente
	public, static e final. Ainda, deve ser declarada em um arquivo com o mesmo nome que o da interface e a
	extensão de arquivo .java.


Factory pattern is one of the most used design patterns in Java. This type of design pattern comes under creational pattern as
 this pattern provides one of the best ways to create an object.

In Factory pattern, we create object without exposing the creation logic to the client and refer to newly created object using
 a common interface.
 
## Implementation

We're going to create a Shape interface and concrete classes implementing the Shape interface. A factory class ShapeFactory is
 defined as a next step.

FactoryPatternDemo, our demo class will use ShapeFactory to get a Shape object. It will pass information (CIRCLE / RECTANGLE / SQUARE)
 to ShapeFactory to get the type of object it needs.
 
 <image src="https://github.com/shnonomura/diarioProgramacao/blob/master/imagem/shape_factory.jpg">


### Step 01

**Create an interface.**

Shape.java

	public interface Shape {
	   void draw();
	}

### Step 2

**Create concrete classes implementing the same interface.**

Rectangle.java

	public class Rectangle implements Shape {

	   @Override
	   public void draw() {
	      System.out.println("Inside Rectangle::draw() method.");
	   }
	}

Square.java

	public class Square implements Shape {

	   @Override
	   public void draw() {
	      System.out.println("Inside Square::draw() method.");
	   }
	}

Circle.java

	public class Circle implements Shape {

	   @Override
	   public void draw() {
	      System.out.println("Inside Circle::draw() method.");
	   }
	}

### Step 3

**Create a Factory to generate object of concrete class based on given information.**

ShapeFactory.java

	public class ShapeFactory {
		
	   //use getShape method to get object of type shape 
	   
	   public Shape getShape(String shapeType){
	   
	      if(shapeType == null){
		 return null;
	      }		
	      if(shapeType.equalsIgnoreCase("CIRCLE")){
		 return new Circle();
		 
	      } else if(shapeType.equalsIgnoreCase("RECTANGLE")){
		 return new Rectangle();
		 
	      } else if(shapeType.equalsIgnoreCase("SQUARE")){
		 return new Square();
	      }
	      
	      return null;
	   }
	}

### Step 4

**Use the Factory to get object of concrete class by passing an information such as type.**

FactoryPatternDemo.java

	public class FactoryPatternDemo {

	   public static void main(String[] args) {
	      ShapeFactory shapeFactory = new ShapeFactory();

	      //get an object of Circle and call its draw method.
	      Shape shape1 = shapeFactory.getShape("CIRCLE");

	      //call draw method of Circle
	      shape1.draw();

	      //get an object of Rectangle and call its draw method.
	      Shape shape2 = shapeFactory.getShape("RECTANGLE");

	      //call draw method of Rectangle
	      shape2.draw();

	      //get an object of Square and call its draw method.
	      Shape shape3 = shapeFactory.getShape("SQUARE");

	      //call draw method of square
	      shape3.draw();
	   }
	}

### Step 5

**Verify the output.**

Inside Circle::draw() method.

Inside Rectangle::draw() method.

Inside Square::draw() method.