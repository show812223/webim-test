<script setup lang="ts">

// 抽象類別（Abstraction）
abstract class Animal {
  // 封裝（Encapsulation）：name 是 protected，無法直接外部存取
  protected name: string;
  constructor(name: string) {
    this.name = name;
  }
  // 提供公開方法 getName() 來存取 name（封裝）
  public getName(): string {
    return this.name;
  }
  // 抽象方法，讓子類別各自實作（Abstraction）
  abstract makeSound(): string;
}

// 繼承（Inheritance）：Dog 繼承 Animal
class Dog extends Animal {
  makeSound(): string {
    return "汪汪"; // 實作 makeSound（多型）
  }
}

// 繼承（Inheritance）：Cat 繼承 Animal
class Cat extends Animal {
  makeSound(): string {
    return "喵喵"; // 實作 makeSound（多型）
  }
}

const animals = ref<Animal[]>([
    new Dog("Buddy"),
    new Cat("Kitty"),
])

const sound = ref<string>("");


// 多型（Polymorphism）：接受 Animal 類型，並呼叫 makeSound()
function printAnimalSound(animal: Animal): void {
  console.log(animal.makeSound());
  sound.value = animal.makeSound();

}

</script>

<template>
  <p>sound: {{ sound }}</p>
<v-btn v-for="animal in animals" @click="printAnimalSound(animal)">{{animal.getName()}}</v-btn>
</template>

<style scoped>

</style>
