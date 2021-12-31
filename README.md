# Learning-rust
Learning rust from scratch. 

The Rust book: https://doc.rust-lang.org/stable/book/
<br />
[Youtube video Tutorial](https://www.youtube.com/watch?v=OX9HJsJUDxA&list=PLai5B987bZ9CoVR-QEIN9foz4QCJ0H2Y8)
<br />

# Examples

> ## Guessing_game.rs
```
use std::io;
use rand::Rng;
use std::cmp::Ordering;
use colored::*;

 
fn main(){
    println!("Guessing game!!!");
    let secret_number = rand::thread_rng().gen_range(1,101);
    loop {
        println!("please input the number?");
        let mut guess = String:: new();
        io::stdin()
            .read_line(&mut guess)
            .expect("Failed to read the message");
        let guess: u32 = match guess.trim().parse() {
            Ok(num) => num,
            Err(_) => continue,
        };

        println!("The guessed number is : {}",guess);
        println!("The random  number is : {}",secret_number);
        match guess.cmp(&secret_number){
            Ordering::Less => println!("{}", "Too small".red()),
            Ordering::Greater=> println!("{}", "Too big".red()),
            Ordering::Equal =>{ 
                println!("{}","you win!".green());
                break;
            }
        }
        
    }
}
```
 
