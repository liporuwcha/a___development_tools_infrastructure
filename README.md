# a___development_tools_infrastructure

***liporuwcha namespace a__ development tools, infrastructure***

 ![logo](https://github.com/liporuwcha/liporuwcha/blob/main/images/logo/logo_liporuwcha.png)  
 liporuwcha is a "GitHub organization" that groups [multiple repositories](https://github.com/orgs/liporuwcha/repositories?q=sort%3Aname-asc) together

 ![work-in-progress](https://img.shields.io/badge/work_in_progress-yellow)
 ![rustlang](https://img.shields.io/badge/rustlang-orange)
 ![postgres](https://img.shields.io/badge/postgres-orange)
 ![License](https://img.shields.io/badge/license-MIT-blue.svg)
 ![a___development_tools_infrastructure](https://bestia.dev/webpage_hit_counter/get_svg_image/1773735898.svg)

## a___ development tools, infrastructure

Before any software project we need to talk about the development tools and infrastructure.  
There are so many options that one can be lost in a maze of choices and never ever leave it with something concrete.  
Limiting the choice and freedom will boost the productivity. Human brains are capable of doing very few thing simultaneously.

### aa__ operating systems

There are many operating systems in the world. We have to limit our learning and effort to be productive.

#### aaa_ Linux

Linux is my operating system of choice. It is open-source and free and it runs most of the internet servers. It does not need to have a graphic user interface for running databases and web servers. I like to use Debian for its stability. We will not experiment new things on the server side.  

#### aab_ Windows

I have [Windows](https://github.com/CRUSTDE-ContainerizedRustDevEnv/windows_reinstall) on my laptop, but I will not use it directly for development.

#### aac_ WSL on Windows  

We can have simultaneously Linux and Windows on the machine using [WSL - Windows Subsystem for Linux](https://github.com/CRUSTDE-ContainerizedRustDevEnv/win10_wsl2_debian11). It works fine for me.

#### aad_ android  

On my phone I have android. It will not matter for this project.

#### aae_ MacOS and iOS  

I will avoid doing anything directly on these OS.

#### aaj_ virtual machines  

OS can run on bare metal or inside a VM virtual machine. VM are great to isolate simpler things running on one beefy machine.

#### aak_ Linux containers  

Linux has [containers](https://github.com/CRUSTDE-ContainerizedRustDevEnv/crustde_cnt_img_pod) that are kind of small VM. It is not a perfect equivalent, but it is good for isolation, albeit not great. I know about Docker, but I choose to use the alternative Podman instead. I like to have my development environment inside a container [CRUSTDE](https://github.com/CRUSTDE-ContainerizedRustDevEnv).

### ab__ networks

#### aba_ tcp, ip and udp  

The Internet protocol suite is the basis of internet communication. I will not use them directly.

#### abb_ web http request-response  

This protocol is simple to think about and strong enough for most of the internet. The client sends a request and the server reply with a response. Nothing more to see here.

#### abc_ websockets  

Finally there is a simultaneous two-way communication channel on the internet.

#### abd_ http2  

I don't know. I hope it is just an upgrade and it is backward compatible.

#### abe_ http3  

I don't know. I hope it is just an upgrade and it is backward compatible.

#### abf_ server-sent events  

SSE allows the server to push data to the client.

#### abg_ SSL, TLS and HTTPS  

This technology is securing the internet connection by encrypting data sent between a website and a browser.

#### abj_ ssh  

The SSH protocol is the standard way for remote work and file copy in Linux.

#### abk_ REST api  

REST API is a way of accessing web services in a simple and flexible way without having any processing. But I need something simpler than that.

### ad__ postgres database

#### ada_ database servers  

I run the Postgres server on Linux directly or in a container. The default port is 5432. In the container I use SSH tunneling to forward the port 5432, so I can connect to the server from Windows.

#### adb_ database config

The initial databases of postgres are: `postgres`, `template1` and `template0`. We should create a new database.

#### adc_ users and roles

The default admin user is called `postgres`. It is wise to create new users for different purposes. It is good to split the admin and normal user.

#### add_ tables, fields, indexes

#### ade_ views, procedures, functions

#### adf_ administrative tools inside the database

#### adg_ database editor VSCode DatabaseClient from Weijan Chen

The VSCode extension to work with Postgres is DatabaseClient. It creates a connection over tcp to the Postgres server. If need, I use SSH tunneling when I use containers.  

#### adj_ SQL language dialect for Postgresql

SQL is the very old standard language for database manipulation (DDL and DML). It is great and easy. But it is also terrible.  
Sql has a terrifyingly incoherent syntax and the same thing can be written in so many ways.
Many tried to create an auto-complete query editor, but it is still a failure, because of the language.  
Sql code can be written in so complicated ways that is impossible to maintain it later. This is a big no-no.  
My First rule of SQL: keep it as simple as possible. Use a limited set of data-types, objects and rules. Keep the syntax as uniform as possible.  
Nobody can or will enforce this and the temptation to make abstract-art code that nobody can maintain is strong.  
Backward compatibility is the killer of readability. I understand that old projects must be maintained with the same "version" of the language they were created. But please let the new projects start with the "fresh new version" that deprecates many old things nobody uses any more. It would be nice for newcomers to have just one easy and simple choice how to write things. A newcomer cannot choose "the best" option from many, because he has no experience. We could give him an easy start deprecating what is not considered "best practice" any more.  
Sadly humans can never agree on anything if it is a matter of aesthetic or opinion. On purpose we wait somebody says something and we say the opposite thing! Then we stick with this opinion forever. Just so, on purpose!  
Uppercase letters for reserved words was a smart thing back in 1970s. But today we have all editors with color syntax highlighting and the old standard is really hard to type. I choose to just code all in lowercase also because that is anyway what postgres internally transforms the code. Different tastes, different opinions, same technical result. We will never agree.  
I like to alias tables in sql queries with one or two letters. I would make it mandatory for all queries, including delete and update. But I cannot.  
I don't see a reason to have the redundant words inner and outer for joins. Everything is crystal clear with join, left join and right join.  
In PL/pgSQL there is confusion between variables and sql object names. There should be a better syntax right from the start. I will prefix input parameters with `i_`, output parameters with `o_` and variables with `v_`. Not very nice, but effective.  
It is not nice to have many columns listed in the same line. It is also not nice to have many columns listed each one on a separate line. The truth is somewhere in between. Maybe 5 columns per line? Maybe column of one table in one line and columns of other table in the other line? There is no answer to that.  
After join, what table column should be on the left side of the comparison? For me it is "logical" the new table is compared with the old table. But somebody thinks exactly the opposite.  
What to use for non-equal: the standard old-school "<>" or the C influenced "!="?
What is the best name for the type: integer, int or int4 ?
What about the varchar, char varying or character varying ?
It is a mess. Does it need to be? No. We just need a benevolent dictator. But nobody has the courage and charisma to be. We wait in a limbo for better days.

#### adk_ function overloading

I despise function overloading in PL/pgSQL. It is a bad idea. Sadly it is impossible to disable. The developer has the burden to be careful. Awful.

#### adl_ case-sensitivity

By default Postgres is case-sensitive. That makes absolute sense for performance. Computers really don't care if "A" is the uppercase of "a". For the computer the first is just the number "65" and the later is the number "97". It is easy to compare this numbers and they are different. End of story.  
Not quite. For us humans they are the same letter, just in uppercase or lowercase. When we order words in a dictionary we (mostly) want to treat them as the same letter. There is code outside the ASCII table that makes this connection. It is very simple for the European languages. You can use the comparison after changing to lowercase: `lower('A')=lower('a')`. It works. Great.  
The sql code and object names in Postgres are also case-sensitive, but they use a trick! Before actually using the code and names they make them lowercase silently in the background. So you can name an object "LaLa", but it will be stored as "lala". Later you can retrieve this object as "LaLa", but in reality the engine will search for the object "lala". Smart trick.  
I personally want my code to be as truthful as possible and these tricks are just messing with my code. So I prefer to write the code and names in their true form all in lowercase.  

#### adm_ unicode collations and utf-8 encoding

What about user text content?  
Don't forget there are more than 7000 spoken languages in the world right now. Most of them want to work something with computers and databases in their language. It is soon overwhelmingly complicated when you need to work with "strange" languages that are not super-similar to English. Just imagine Chinese characters.  
Unicode to the rescue.  
Unicode is more than just mapping of graphemes to a unique number. It is a deep rabbit hole of understanding the few rules and many exceptions of most languages. These rules are often disputed and controversial and change over time.  
The part of the story that compares and orders letters in a language/culture is called "collation".  
The part of unicode that can write and read to a computer file is called "encoding". The preferred encoding is "utf-8". It is ingenious !  
Postgres 13 can use collations. Every text/char/varchar column can have a different collation. That sounds good. But I am afraid that using collation we loose the use of the LIKE operator. And I like the LIKE operator !  
I will try and see going forward.

### ar__ Rust language

#### ara_ Rust language  

[Rust](https://www.rust-lang.org/) is a language empowering everyone to build reliable and efficient software. It is low level as C and does not have a garbage collector. It is striving to be safe against memory bugs.

#### arb_ rust compiler

Rustc is the rust frontend compiler. It uses LLVM for the backend compiler. I like to change the default linker to MOLD.

#### arc_ cargo crate dependencies  

Libraries for Rust are called crates. They are published on [crates.io](https://crates.io/). My personal problem is that I cannot trust these libraries. For one project I need hundreds of them and I just cannot trust them. But there is nothing I can do. It will be fine for hobby projects, but not for any production.

#### ard_ other Rust tools  

They come along the installation like the linter Clippy or separately like cargo-auto.

#### are_ cargo-auto  

All the actions we repeat as developers must be automated. I created the tool [automation_tasks_rs and cargo-auto](https://github.com/automation-tasks-rs) for that purpose.

#### arf_ cross platform compiling  

If needed Rust compiler on Linux can build an executable for Windows. That is nice.

#### ari_ development container crustde  

I like to have my development environment in a [Linux container CRUSTDE](https://github.com/CRUSTDE-ContainerizedRustDevEnv)

#### arj_ VSCode as Rust editor

VSCode is great. I like to use VSCode in Windows and remote connect to the Linux container CRUSTDE in Linux on WSL.

#### ark_ Rust analyzer  

rust-analyzer is an implementation of Language Server Protocol for the Rust programming language. It provides features like completion and goto definition for many code editors, including VS Code.

#### arl_ borrow checker  

Rust memory safety is achieved with these concepts: ownership, borrowing and lifetimes. It is a steep learning curve, but once you learn it, it becomes automatic to think with these concepts in mind.

#### arm_ expressions  

Rust is primarily an expression-based language. Nearly anything can return a value.

#### arn_ variable scope and shadowing  

Variable bindings have a scope, and are constrained to live in a block. A block is a collection of statements enclosed by braces {}. Shadowing is a strange, but useful concept. When we declare a new variable with the same name as a previous variable, the new variable shadows the previous variable. It is really useful, but I critique the choice of making it implicit and not explicit.

#### aro_ Early return

The programming concept of "early return" makes the code much more readable. The "happy path" goes straight through the code till the end of the function. If something is wrong we make an early return from the function. The new language construct "let else statement" is great for this. It is syntactical sugar for match and simplifies some very common error-handling patterns. Before that we had the "if let" and "match" constructs, but they both force "rightward drift" introduce excessive nesting.
Even better is to use the operator "?" for early return where possible. It is very concise and readable.

#### arp_ Rust Workspace

Rust has the concept of "workspace" to group more projects together. But it does not work well if there is a mix of server projects and WASM projects. Because of one WASM project I cannot use the profile `panic="abort"` on all the members.  
I will not use standard cargo workspaces.  
I will use [cargo-auto](https://github.com/automation-tasks-rs/cargo-auto/) to automate the tasks for every member individually.
Then I'll code the `automation_tasks_rs` on the workspace level to call all members tasks together.
The presence of Cargo.toml is used by cargo-auto to recognize project folders.

### ax__ AXUM web server

### as__ SSR server side rendering

### al__ client side rendering

### aw__ WASM/Webassembly, javascript

- aka_ javascript or ecmascript  
I don't like this language. I will avoid it as much as possible.

#### awa_ WebAssembly/WASM  

I will use WASM everywhere it used to be javascript. It can be coded in Rust and compiled to a WASM target.
It works inside all of the modern browsers and even outside of the browser with a wasm runtime.

## Open-source and free as a beer

My open-source projects are free as a beer (MIT license).  
I just love programming.  
But I need also to drink. If you find my projects and tutorials helpful, please buy me a beer by donating to my [PayPal](https://paypal.me/LucianoBestia).  
You know the price of a beer in your local bar ;-)  
So I can drink a free beer for your health :-)  
[Na zdravje!](https://translate.google.com/?hl=en&sl=sl&tl=en&text=Na%20zdravje&op=translate) [Alla salute!](https://dictionary.cambridge.org/dictionary/italian-english/alla-salute) [Prost!](https://dictionary.cambridge.org/dictionary/german-english/prost) [Nazdravlje!](https://matadornetwork.com/nights/how-to-say-cheers-in-50-languages/) 🍻

[//bestia.dev](https://bestia.dev)  
[//github.com/bestia-dev](https://github.com/bestia-dev)  
[//bestiadev.substack.com](https://bestiadev.substack.com)  
[//youtube.com/@bestia-dev-tutorials](https://youtube.com/@bestia-dev-tutorials)  
