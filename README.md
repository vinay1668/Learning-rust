# Learning-rust
Learning rust from scratch. 

The Rust book: https://doc.rust-lang.org/stable/book/
<br />
[Youtube video Tutorial](https://www.youtube.com/watch?v=OX9HJsJUDxA&list=PLai5B987bZ9CoVR-QEIN9foz4QCJ0H2Y8)
<br />

# Examples

<br />

> ## But if we want to really copy the heap data, we can use the clone() method

```
fn main(){
    let s2:String = String::from("hello");
    let s1= s2.clone();
    println!("{}",s1);
    println!("{}",s2);
    
}
```

> ## You will get error because Rust prevents you from using the invalidated reference

```
fn main(){
  let mut s1:String = String::from("Alan Turing");
  let mut s2 = s1;
  println!("{}",s1);

}
```

<br />

> ## This is valid cause integer uses stack for memory allocation.

```
fn main(){
    let x = 3;
    let y = x;
    println!("{}",x);
}

```


> ## Print the lyrics to the Christmas carol “The Twelve Days of Christmas,” taking advantage of the repetition in the song.

```
// Lyrics
// On the first day of Christmas
// My good friends brought to me
// A song and a Christmas tree

// On the second day of Christmas
// My good friends brought to me
// (Two candy canes)
// And a song for the Christmas tree

// On the third day of Christmas
// My good friends brought to me
// (Three boughs of holly)
// (Two candy canes)
// And a song for the Christmas tree

// On the fourth day of Christmas
// My good friends brought to me
// (Four colored lights)
// (Three boughs of holly)
// (Two candy canes)
// And a song for the Christmas tree

// On the fifth day of Christmas
// My good friends brought to me
// (A shining star)
// (Four colored lights)
// (Three boughs of holly)
// (Two candy canes)

// And a song for the Christmas tree
// On the sixth day of Christmas
// My good friends brought to me
// (Little silver bells)
// (A shining star)
// (Four colored lights)
// (Three boughs of holly)
// (Two candy canes)
// And a song for the Christmas tree

// On the seventh day of Christmas
// My good friends brought to me
// (Candles a glowing)
// (Little silver bells)
// (A shining star)
// (Four colored lights)
// (Three boughs of holly)
// (Two candy canes)
// And a song for the Christmas tree

// On the eighth day of Christmas
// My good friends brought to me
// (Gold and silver tinsel)
// (Candles a glowing)
// (Little silver bells)
// (A shining star)
// (Four colored lights)
// (Three boughs of holly)
// (Two candy canes)
// And a song for the Christmas tree

// On the ninth day of Christmas
// My good friends brought to me
// (A guardian angel)
// (Gold and silver tinsel)
// (Candles a glowing)
// (Little silver bells)
// (A shining star)
// (Four colored lights)
// (Three boughs of holly)
// (Two candy canes)
// And a song for the Christmas tree

// On the tenth day of Christmas
// My good friends brought to me
// (Some mistletoe)
// (A guardian angel)
// (Gold and silver tinsel)
// (Candles a glowing)
// (Little silver bells)
// (A shining star)
// (Four colored lights)
// (Three boughs of holly)
// (Two candy canes)
// And a song for the Christmas tree

// On the eleventh day of Christmas
// My good friends brought to me
// (Gifts for one and all)
// (Some mistletoe)
// (A guardian angel)
// (Gold and silver tinsel)
// (Candles a glowing)
// (Little silver bells)
// (A shining star)
// (Four colored lights)
// (Three boughs of holly)
// (Two candy canes)
// And a song for the Christmas tree

// On the twefth day of Christmas
// My good friends brought to me

// And a song for the Christmas tree


use colored::*;

fn main(){
    println!("{}", "Lyrics to the Christmas carol “The Twelve Days of Christmas,".green());
    println!("\n");
    let array_lines = [
    "(All their good wishes)",
    "(Gifts for one and all)",
    "(Some mistletoe)",
    "(A guardian angel)",
    "(Gold and silver tinsel)",
    "(Candles a glowing)",
    "(Little silver bells)",
    "(A shining star)",
    "(Four colored lights)",
    "(Three boughs of holly)",
    "(Two candy canes)" 
    ];
    let array_initial = [
        "On the first day of Christmas",
        "My good friends brought to me",
         "A song and a Christmas tree" 
    ];
    let array_second =[
        "My good friends brought to me",
         //(Two candy canes)
        "And a song for the Christmas tree"
    ];
    let array_linear =[
        "On the second day of Christmas",
        "On the third day of Christmas",
        "On the fourth day of Christmas",
        "On the fifth day of Christmas",
        "On the sixth day of Christmas",
        "On the seventh day of Christmas",
        "On the eighth day of Christmas",
        "On the nineth day of Christmas",
        "On the tenth day of Christmas",
        "On the eleventh day of Christmas",
        "On the twefth day of Christmas"


    ];
    for i in 0..3{
        println!("{}",array_initial[i]);
    }
    println!("\n");
    for i in 0..11{

        for j in 0..2{
            if j == 1 {
                for k in (1..i+2).rev() {
                    if k!=0 {
                    println!("{}",  array_lines[array_lines.len()-k] );
                    }
                    

                }

            println!("{}",array_second[j]);
            }
            else{
                if j == 0{
                    println!("{}",array_linear[i]);

                }
            println!("{}",array_second[j]);
            }
        }
    println!("\n");   
    }
   
}
```
<br />


>  ## Output of the above program.

```
   Compiling guessing_game v0.1.0 (D:\Desktop\rust\projects\guessing_game)
    Finished dev [unoptimized + debuginfo] target(s) in 0.85s
     Running `target\debug\guessing_game.exe`
Lyrics to the Christmas carol “The Twelve Days of Christmas,


On the first day of Christmas    
My good friends brought to me    
A song and a Christmas tree      


On the second day of Christmas   
My good friends brought to me    
(Two candy canes)
And a song for the Christmas tree


On the third day of Christmas    
My good friends brought to me    
(Three boughs of holly)
(Two candy canes)
And a song for the Christmas tree


On the fourth day of Christmas
My good friends brought to me
(Four colored lights)
(Three boughs of holly)
(Two candy canes)
And a song for the Christmas tree


On the fifth day of Christmas
My good friends brought to me
(A shining star)
(Four colored lights)
(Three boughs of holly)
(Two candy canes)
And a song for the Christmas tree


On the sixth day of Christmas
My good friends brought to me
(Little silver bells)
(A shining star)
(Four colored lights)
(Three boughs of holly)
(Two candy canes)
And a song for the Christmas tree


On the seventh day of Christmas
My good friends brought to me
(Candles a glowing)
(Little silver bells)
(A shining star)
(Four colored lights)
(Three boughs of holly)
(Two candy canes)
And a song for the Christmas tree


On the eighth day of Christmas
My good friends brought to me
(Gold and silver tinsel)
(Candles a glowing)
(Little silver bells)
(A shining star)
(Four colored lights)
(Three boughs of holly)
(Two candy canes)
And a song for the Christmas tree


On the nineth day of Christmas
My good friends brought to me
(A guardian angel)
(Gold and silver tinsel)
(Candles a glowing)
(Little silver bells)
(A shining star)
(Four colored lights)
(Three boughs of holly)
(Two candy canes)
And a song for the Christmas tree


On the tenth day of Christmas
My good friends brought to me
(Some mistletoe)
(A guardian angel)
(Gold and silver tinsel)
(Candles a glowing)
(Little silver bells)
(A shining star)
(Four colored lights)
(Three boughs of holly)
(Two candy canes)
And a song for the Christmas tree


On the eleventh day of Christmas
My good friends brought to me
(Gifts for one and all)
(Some mistletoe)
(A guardian angel)
(Gold and silver tinsel)
(Candles a glowing)
(Little silver bells)
(A shining star)
(Four colored lights)
(Three boughs of holly)
(Two candy canes)
And a song for the Christmas tree


On the twefth day of Christmas
My good friends brought to me
(All their good wishes)
(Gifts for one and all)
(Some mistletoe)
(A guardian angel)
(Gold and silver tinsel)
(Candles a glowing)
(Little silver bells)
(A shining star)
(Four colored lights)
(Three boughs of holly)
(Two candy canes)
And a song for the Christmas tree

```
<br />


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
 
