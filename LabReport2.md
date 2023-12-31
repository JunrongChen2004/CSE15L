# Lab Report 2
Junrong Chen

## Part 1:
```Java
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;
import java.util.List;

class StringHandler implements URLHandler {
    private List<String> messages = new ArrayList<>();
    private int sequenceNumber = 1;

    public String handleRequest(URI url) {
        if (url.getPath().equals("/add-message")) {
            String query = url.getQuery();
            String[] parts = query.split("=");
            if (parts.length == 2 && parts[0].equals("s")) {
                String message = parts[1];
                messages.add(sequenceNumber + ". " + message);
                sequenceNumber++;
                return String.join("\n", messages);
            }
        }
        return "Hello StringServer";
    }
}

class StringServer {
    public static void main(String[] args) throws IOException {
        if (args.length == 0) {
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new StringHandler());
    }
}
```
![Adding1](https://github.com/JunrongChen2004/CSE15L/assets/122309066/05740815-0fd6-4ee2-b4f7-37621c356661)
![Adding2](https://github.com/JunrongChen2004/CSE15L/assets/122309066/c454a4ba-0d26-4542-b25e-7ecc74d255d7)

### Which methods in your code are called?
A method called handleRequest in my code and main method was called

### What are the relevant arguments to those methods, and the values of any relevant fields of the class?
/add-message?s=pineapple; messages is initially empty, sequenceNumber is initially 1
/add-message?s=hello; messages contains "1. Pineapple", sequenceNumber is 2.

### How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why
After the request, messages contains "1. Hello", and sequenceNumber is incremented to 2.
After the request, messages now contains "1. Hello\n2. How are you", and sequenceNumber is incremented to 3.

## Part 2:

### Location of Private Key: id_rsa
![Private&Public Key](https://github.com/JunrongChen2004/CSE15L/assets/122309066/8f267a11-2b9d-43b2-9842-6189e5cbe835)
![without password](https://github.com/JunrongChen2004/CSE15L/assets/122309066/473c0236-472d-4387-884a-438b70e69a7f)
Private key is located in id_rsa.

## Part 3:

I've learn how to go onto remote machine, how to generate ssh, how to write a web server and play with it, how to use basic bash languages in terminal, how to create account and use github, and how to use markdown to write web pages on github.
