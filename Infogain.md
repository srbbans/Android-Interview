# I N F O G A I N 


# Round 1:- 

   - Theoratical
 
    > Thread lifeCycles
    > Diff bitween Wait() and Sleep()
    > Diff between Start and Run()
    > Join method
    > How to JOIN 3 thread T1< T2< T3, as start ater one another.
    > Threads Priority,
    > Syncronization
    > Double check locking
    > Comparator Vs Comparable
    > Can we call Start 2 times on a Thread();
    > Thread Related Programms Questions.


  - Coding Problems

    - Guess the output:
      
          class Threading {
             public static void main(String[] args) {
                 test();
             }
              private static void test() {
                  try {
                      System.out.println("In try");
                      throw new ArithmeticException();
                  } catch (Exception e) {
                      System.out.println("In catch");
                      throw new ArrayIndexOutOfBoundsException();
                  } finally {
                      System.out.println("In finally");
                      throw new NullPointerException();
                  }
              }
          }


   - Guess the output:
    
          class Threading {
              public static void main(String[] args) {
                  System.out.println("Value of a :" + test());
              }

              private static int test() {
                  int a = 10;
                  try {
                      return a;
                  } catch (Exception e) {
                      a = 20;
                      System.out.println("a in catch : " + a);
                  } finally {
                      a = 30;
                      System.out.println("a in finally : " + a);
                  }
                  a = 40;
                  System.out.println("a outside try-catch : " + a);
                  return a;
              }
          }

