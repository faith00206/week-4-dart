class Animal {
  String name;
  
  Animal(this.name);
  
  void speak() {
    print('$name speaks');
  }
}

class Dog extends Animal {
  Dog(String name) : super(name);
  
  @override
  void speak() {
    print('$name barks');
  }

abstract class CanFly {
  void fly();
}

class Bird extends Animal implements CanFly {
  Bird(String name) : super(name);
  
  @override
  void speak() {
    print('$name chirps');
  }
  
  @override
  void fly() {
    print('$name flies');
  }
}

class Cat extends Animal {
  Cat(String name) : super(name);
  
  @override
  void speak() {
    print('$name meows');
  }
}

class FileReader {
  static List<String> readFile(String fileName) {
    // Simulated file reading process
    return ['Fido', 'Whiskers', 'Tweety'];
  }
}

void main() {
  List<String> names = FileReader.readFile('animals.txt');
  
  // Create instances of classes initialized with data from a file
  List<Animal> animals = [];
  for (String name in names) {
    animals.add(Dog(name));
  }
  void makeAnimalsSpeak() {
    for (Animal animal in animals) {
      animal.speak();
    }
  }
  
  makeAnimalsSpeak();
}
