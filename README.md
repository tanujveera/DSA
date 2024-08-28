# DSA

[All divisors of a number N](https://www.geeksforgeeks.org/problems/all-divisors-of-a-number/1)

Instead of checking all the numbers. Take the square root of the given number N. Iterate till square root of N. 
After sqrt(N), all the divisors will be repeated to save time complexity.

```java
public static void print_divisors(int N) {
        // code here
        List<Integer> list = new ArrayList<>();
        /* for(int i = 1; i*i<=N; i++){
            Instead of using sqrt(N) which takes alot of mathematical computation. 
            We can use i*i<=N. Lets say N= 49 when i reaches 7, i*i = 7*7 which is 49, and in next iteration, 8*8 = 64 > 49.
            Efficient way
        */
        for(int i = 1; i<=Math.sqrt(N); i++){
            if(N % i == 0){
                list.add(i);
                if((N/i) != i){
                    list.add(N/i);
                }
            }
        }
        Collections.sort(list);
        list.forEach(l -> System.out.print(l+" "));
    }
```

[Prime Numbers](https://www.geeksforgeeks.org/problems/prime-number2314/1)

Using the factorial method, we can find the prime numbers as the prime number has only 2 factors - 1 and number itself.
We have to check if it has only 2 factors.

```java
    static int isPrime(int N){
        // code here
        int counter = 0;
         for(int i = 1; i*i<=N; i++){
            if(N % i == 0){
                counter ++;
                if((N/i) != i){
                    counter++;
                }
            }
        }
      return counter == 2 ? 1 : 0; // prime : not prime
    }
```