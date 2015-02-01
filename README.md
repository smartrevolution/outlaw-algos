# Outlaw Algorithms
Bandit Algorithms in Clojure

This lib is meant to be used from other JVM languages.

Here is an example how to use it from Java:

```java
import java.util.Random;
import outlawalgos.*;

public class Outlaw {
    public static void main(String[] args) {
	int arm = 0;
	Random r = new Random();
	
	MultiarmedBandit b = new MultiarmedBandit(0.1, 5);
	for (int i=0; i < 10; i++) {
	    arm = b.selectArm();
	    double reward = r.nextDouble() > 0.9 ? 0.0:1.0;
	    b.updateReward(arm, reward);
	    System.out.println(b);
	}	
	System.exit(0);
    }
}
```

