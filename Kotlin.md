# Kotlin - Data classes can be inherited?

    Q: I need to inherit a data class A from data class B?
    
    - this is not feasible in Kotlin.

    Question 1:
    Why is this not feasible?
    - Data class contains some generated methods, like hashCode, equals, copy,... You could break those methods in class extending data class, but kotlin needs to guarantee that they work properly. That's the reason for making data class impossible to extend.


    Question 2:
    What may be a solution for this?
    - The only solution for that, when you need two data class is to create one more abstract class and derive these two data classes from it. You need to notice that data class in kotlin create hashcode, equals and toString, and other methods based on primary constructor, and that's why you need to override fields from Base class in data class constructor.

    > :

      abstract class Base(open val data1: String)

      data class A(override val data1: String): Base(data1)

      data class B(override val data1: String,  val data2: String): Base(data1)
