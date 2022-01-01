# Learning-rust
Learning rust from scratch. 

The Rust book: https://doc.rust-lang.org/stable/book/
<br />
[Youtube video Tutorial](https://www.youtube.com/watch?v=OX9HJsJUDxA&list=PLai5B987bZ9CoVR-QEIN9foz4QCJ0H2Y8)
<br />

# Examples

> ## Generate the nth Fibonacci number.
```
use std::io;
use colored::*;
fn main(){
    println!("{}","Program to generate the nth Fibonacci number!".green());
    println!("please input the Fibonacci number position");
    let mut nth_number = String::new();
    io::stdin().read_line(&mut nth_number).expect("Please input the number.");
    let nth_number:usize = nth_number.trim().parse().expect("Please input the number");
    let mut first_number = 0;
    let mut second_number = 1;
    let mut xs = Vec::new();
    xs.push(0);
    xs.push(1);
    for element in 3..(nth_number+1){
        let third_number = first_number + second_number;
        first_number = second_number;
        second_number = third_number;
        xs.push(third_number);
    }
    println!("The {} th number in the fibonacci series is: {}", nth_number, xs[nth_number-1]);
    for element in xs{
        println!("{}",element);
    }

}
```
<br/>

> ## Convert temperatures between Fahrenheit and Celsius.
```
use std::io;
use colored::*;
fn main(){
    println!("{}","program for the conversion of fahrenheit and celsius!".green());
    println!("Press 1 to convert from fahrenheit to celsius:");
    println!("Press 2 to convert from celsius to fahrenheit:");
    let mut number = String::new();
    io::stdin().read_line(&mut number).expect("please choose the option!");
    let number:i32 = number.trim().parse().expect("please input the number");
    if number == 1{
        println!("Please input the fahrenheit temperature!");
        let mut fah_num = String::new();
        io::stdin().read_line(&mut fah_num).expect("please input the fahrenheit");  
        let fah_num:i32 = fah_num.trim().parse().expect("please input the number");  
      //(325°F − 32) × 5/9
        let deg_cel:i32 = (fah_num - 32) * 5/9 ;
        println!("The degree celsius are :{}",deg_cel);
    }
    else if number == 2 {
        println!("Please input the celsius temperature!");
        let mut cel_num = String::new();
        io::stdin().read_line(&mut cel_num).expect("please input the celsius");  
        let cel_num:i32 = cel_num.trim().parse().expect("please input the number");    
      //(325°F − 32) × 5/9
        let deg_fah:i32 = (cel_num * 9/5) + 32;
        println!("The degree fahrenheit is :{}",deg_fah);     
    }
}

```
<br />

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
 
