Download Link: https://assignmentchef.com/product/solved-cs1331-homework-11-pokemon
<br>
<h1>Problem Description</h1>

Struck by sudden nostalgia, you quit your job and start playing games from your childhood, like Pokemon! However, life seems determined to make you a Software Engineer. One day, as you sit huddled underneath a blanket snacking on saltine crackers, your DS suddenly glows bright blue. You shield your eyes, and when you open them you find yourself in the world of Pokemon. You immediately walk to the nearest Pokemon Center that you know is 108.15 yards to your right. Nurse Joy is very kind to you, but after watching her treat the injured Pokemon, you realize she is overworked and extremely disorganized. This calls for some programming!

<h1>Solution Description</h1>

For this assignment, create the following files:

<ul>

 <li>java</li>

 <li>java</li>

 <li>java</li>

 <li>java</li>

</ul>

<strong>Pokemon Class:</strong>

Implements the <a href="https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/lang/Comparable.html">Comparable interface</a>. A pokemon is “greater” when it has more health; a pokemon is “lesser” when it has less health. Should be abstract.

<em>Instance Variables</em>:

<ul>

 <li>medicalHistory, an ArrayList of Integers that tracks changes to the pokemon’s health. For example, if a pokemon loses 5 health, -5 should be appended to medicalHistory. As another example, if a pokemon gains 7 health, 7 should be appended to medicalHistory. This instance variable should have private access.</li>

 <li>trainerName, a String which is the pokemon’s trainer’s name. It should have private access.</li>

 <li>health, an int that is the pokemon’s health. It should have private access.</li>

 <li>maxHealth, an int that is the pokemon’s maximum health. It should have private access.</li>

</ul>

<em>Constructors</em>:

<ul>

 <li>Pokemon(String trainerName, int health, int maxHealth) <strong>– </strong>Sets trainerName, health and maxHealth properly.</li>

</ul>

<strong>– </strong>Initializes an empty ArrayList of Integers for medicalHistory.

<ul>

 <li>Pokemon(Pokemon p) copy-constructor, provides a deep copy of the object.</li>

</ul>

<em>Methods</em>:

<ul>

 <li>void heal(int amount) increase health by specified amount. However, health cannot be greater than maxHealth. In cases where health plus amount is greater than maxHealth, set health to maxHealth. Because health has changed, make sure to update medicalHistory. Only update with actual (not expected) change to health. For example, if a pokemon has a health of 6, maxHealth of 7, and is healed by amount 5, only append 1 to medicalHistory. As another example, if a pokemon has health 8, maxHealth 8, and is healed by amount 2, append 0 to medicalHistory.</li>

 <li>void damage(int amount) decrease health by the specified amount. However, health cannot go below 0. In cases where decreasing health by the specified amount makes health negative, set health to 0 and update medicalHistory with only the amount of health lost; for example, if a pokemon has 3 health and takes 4 damage, you would append -3 to its medicalHistory.</li>

 <li>int compareTo(Pokemon other) A pokemon is “greater” when it has more health; a pokemon is “lesser” when it has less health.</li>

 <li>boolean equals(Object other) Pokemon are considered equal if they have the same trainerName, health, maxHealth, and medicalHistory.</li>

 <li>int hashCode() Write a proper hashCode for Pokemon that contains the proper fields. Only use the maxHealth field to compute the hash code.</li>

 <li>Getters for trainerName, health, and maxHealth.</li>

 <li>Setter for trainerName.</li>

</ul>

<strong>Pikachu Class:</strong>

Is a subclass of Pokemon <em>Instance Variables</em>:

<ul>

 <li>int friendshipLevel the level of friendship the pikachu has with its trainer. It should have private access.</li>

</ul>

<em>Constructors</em>:

<ul>

 <li>Pikachu(String trainerName, int health, int maxHealth, int friendshipLevel) sets trainerName, health, maxHealth, and friendshipLevel properly.</li>

 <li>Pikachu(Pikachu p) copy-constructor, provides a deep copy of the object.</li>

</ul>

<em>Methods</em>:

<ul>

 <li>void heal(int amount) increase health by twice the amount because pikachus heal quickly. However, health cannot be greater than maxHealth. In cases where health plus amount is greater than maxHealth, set health to maxHealth. Because health has changed, make sure to update medicalHistory. Only update with actual (not expected) change to health. Reuse code if possible!</li>

 <li>boolean equals(Object other) Pikachus are considered equal if they have the same trainer, health, maxHealth, medicalHistory, and friendshipLevel. Reuse code if possible!</li>

 <li>int hashCode() Write a proper hashCode for Pikachu that contains the proper fields. Use the fields maxHealth and friendshipLevel for computing the hash code.</li>

</ul>

<strong>Charmander Class:</strong>

Is a subclass of Pokemon <em>Instance Variables</em>:

<ul>

 <li>int flameLevel represents how much flame the charmander has. It should have private access.</li>

</ul>

<em>Constructors</em>:

<ul>

 <li>Charmander(String trainerName, int health, int maxHealth, int flameLevel) sets trainerName, health, maxHealth, and flameLevel properly.</li>

 <li>Charmander(Charmander c) copy-constructor, provides a deep copy of the object.</li>

</ul>

<em>Methods</em>:

<ul>

 <li>boolean equals(Object other) Charmanders are considered equal if they have the same trainer, health, maxHealth, medicalHistory, and flameLevel. Reuse code if possible!</li>

 <li>int hashCode() Write a proper hashCode for Charmander that contains the proper fields. Use the fields maxHealth and flameLevel for computing the hash code.</li>

 <li>void damage(int amount, boolean isWaterDamage) decrease health by amount if it is not water damage. if it is water damage, decrease health by twice the amount. Health cannot go below 0. In cases where health falls below 0, set health to 0 and update medicalHistory with only the amount of health lost; for example, if a pokemon has 3 health and takes 4 damage, you would append -3 to its medicalHistory. Make sure to update medicalHistory accordingly and reuse code wherever possible!</li>

</ul>

<strong>PokemonCenter Class:</strong>

<em>Instance Variables</em>

<ul>

 <li>injured, an ArrayList of pokemon that holds the injured pokemon in line to be treated. The list should be ordered by how recently a pokemon was seen. Most recently seen pokemon are always at the end of the list. It should have private access.</li>

 <li>nurses, an int that is the number of nurses at the Pokemon Center. It should have private access.</li>

</ul>

<em>Constructors</em>:

<ul>

 <li>PokemonCenter(ArrayList&lt;Pokemon&gt; injured, int nurses) sets the two instance variables to the provided values.</li>

 <li>PokemonCenter() sets the two instance variables to their default values; empty ArrayList of injured pokemon and one nurse.</li>

</ul>

<em>Methods</em>:

<ul>

 <li>boolean add(Pokemon pokemon) adds a pokemon to the list of injured pokemon, regardless of whether or not it is injured. Always add to the end of the injured Just make sure that a pokemon isn’t already on the list! This method returns true if a pokemon was added, else false.</li>

 <li>void heal(int amount). For each nurse in the center, remove a pokemon from the list and increase its health by the specified amount. If there are more nurses than pokemon in the list, simply heal each pokemon once. If (after healing) a pokemon is not fully healed, add it to the list of injured Pokemon. Remember, most recently seen pokemon go at the end!</li>

 <li>void healMostInjured(int amount). Sort the list, putting the most injured pokemon in the front and the least injured pokemon in the back. (HINT: Check out the <a href="https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/Collections.html">Collections class</a>) Then, for each nurse in the center, remove a pokemon from the front of the list and increase its health by the specified amount. If there are more nurses than pokemon in the list, simply heal each pokemon once. If the pokemon isn’t fully healed, add it back to the list. Make sure that after this method finishes executing, injured is still ordered by how recently a pokemon has been seen. (most recently seen pokemon go at the end!)</li>

 <li>String toString() which returns “This Pokemon Center has [number of nurses] nurses and [number of pokemon in injured list] pokemon waiting to be seen.”</li>

</ul>

<strong>Testing your code:</strong>

If you want to test out your own code before submitting we recommend creating a separate java file and implementing a main method there. You can then create new animals and test your methods. Below is some sample testing code. <strong>These tests are not comprehensive!</strong>

Pikachu pikachu = <strong>new </strong>Pikachu(“Ryan”, 20, 25, 10);

Pikachu pikachu2 = <strong>new </strong>Pikachu(pikachu);

Charmander charmander = <strong>new </strong>Charmander(“Emma”, 20, 30, 10);

Charmander charmander2 = <strong>new </strong>Charmander(“Emma”, 10, 30, 10);

System.out.println(pikachu.equals(pikachu2)); <em>// True </em>pikachu.heal(10);

System.out.println(pikachu.equals(pikachu2)); <em>// False</em>

PokemonCenter pokemonCenter = <strong>new </strong>PokemonCenter();

pokemonCenter.add(charmander2); pokemonCenter.add(charmander); pokemonCenter.healMostInjured(7); <em>//charmander2 health = 17 now</em>

Feel free to create your own tests in the main method! Try to write tests for the remaining methods in the file!

<h1>Rubric</h1>

<ul>

 <li>[35] Pokemon

  <ul>

   <li>[5] heal(int)</li>

   <li>[5] damage(amount)</li>

   <li>[5] equals(Object)</li>

   <li>[5] compareTo(Pokemon)</li>

   <li>[5] hashCode()</li>

   <li>[5] Copy-constructor assigns properly</li>

   <li>[2.5] Constructor with four parameters assigns properly</li>

   <li>[2.5] Specified getters and setters</li>

  </ul></li>

 <li>[15] Pikachu

  <ul>

   <li>[2.5] heal(int) reuses code</li>

   <li>[5] equals(Object) reuses code</li>

   <li>[2.5] hashCode()</li>

   <li>[2.5] Copy-constructor assigns properly</li>

   <li>[2.5] Constructor with four parameters assigns properly</li>

  </ul></li>

 <li>[15] Charmander

  <ul>

   <li>[2.5] damage(int, boolean) reuses code</li>

   <li>[5] equals(Object) reuses code</li>

   <li>[2.5] hashCode()</li>

   <li>[2.5] Copy-constructor assigns properly</li>

   <li>[2.5] Constructor with four parameters assigns properly</li>

  </ul></li>

 <li>[35] PokemonCenter

  <ul>

   <li>[5] add(Pokemon)</li>

   <li>[10] heal()</li>

   <li>[10] healMostInjured()</li>

   <li>[5] toString()</li>

   <li>[2.5] Constructor with two parameters assigns properly</li>

   <li>[2.5] Constructor with zero parameters assigns properly</li>

  </ul></li>

</ul>

<h1>Allowed Imports</h1>

<ul>

 <li>To prevent trivialization of the assignment, you are only allowed to import the following class: <strong>– </strong>java.util.ArrayList</li>

</ul>

<strong>– </strong>java.util.Collections

<h1>Javadocs</h1>

For this assignment, you will be commenting your code with Javadocs. Javadocs are a clean and useful way to document your code’s functionality. For more information on what Javadocs are and why they are awesome, the <a href="http://www.oracle.com/technetwork/java/javase/documentation/index-137868.html">online overview</a> for them is extremely detailed and helpful.

You can generate the javadocs for your code using the command below, which will put all the files into a folder called javadoc:

$ javadoc *.java -d javadoc

The relevant tags that you need to include are @author, @version, @param, and @return. Here is an example of a properly Javadoc’d class:

<table width="632">

 <tbody>

  <tr>

   <td width="632"><strong>import </strong>java.util.Scanner;<em>/**</em>* This class represents a Dog object<em>.</em>* <strong>@author </strong>George P<em>. </em>Burdell* <strong>@version </strong><em>1.0</em><em>*/ </em><strong>public class </strong>Dog {<em>/**</em>* Creates an awesome dog <em>(</em>NOT a dawg<em>!) */</em><strong>public </strong>Dog() { …}<em>/**</em>* This method takes in two ints and returns their sum* <strong>@param a </strong>first number* <strong>@param b </strong>second number <em>* </em><strong>@return </strong>sum of a and b<em>*/</em><strong>public </strong>int add(int a, int b) {…}}</td>

  </tr>

 </tbody>

</table>

A more thorough tutorial for Javadocs can be found <a href="https://cs1331.gitlab.io/cs1331-style-guide.html">here</a>. Take note of a few things:

<ol>

 <li>Javadocs are begun with /** and ended with */.</li>

 <li>Every class you write must be Javadoc’d and the @author and @verion tag included. The comments for a class should start with a brief description of the role of the class in your program.</li>

 <li>Every non-private method you write must be Javadoc’d and the @param tag included for every method parameter. The format for an @param tag is @param &lt;name of parameter as written in method header&gt; &lt;description of parameter&gt;. If the method has a non-void return type, include the @return tag which should have a simple description of what the method returns, semantically.</li>

</ol>


