# a_development_tools_infrastructure

***liporuwcha namespace "a - development tools, infrastructure"***

 ![work-in-progress](https://img.shields.io/badge/work_in_progress-yellow)
 ![rustlang](https://img.shields.io/badge/rustlang-orange)
 ![postgres](https://img.shields.io/badge/postgres-orange)
 ![a_development_tools_infrastructure](https://bestia.dev/webpage_hit_counter/get_svg_image/1773735898.svg)

## a - development tools, infrastructure

Before any software project we need to talk about the development tools and infrastructure.  
There are so many options that one can be lost in a maze of choices and never ever leave it with something concrete.  
Limiting the choice and freedom will boost the productivity. Human brains are capable of doing very few thing simultaneously.

### aa - operating systems

There are many operating systems in the world. We have to limit our learning and effort to be productive.

- aaa - Linux  
Linux is my operating system of choice. It is open-source and free and it runs most of the internet servers. It does not need to have a graphic user interface for running databases and web servers. I like to use Debian for its stability. We will not experiment new things on the server side.  

- aab - Windows  
I have [Windows](https://github.com/CRUSTDE-ContainerizedRustDevEnv/windows_reinstall) on my laptop, but I will not use it directly for development.
- aac - WSL on Windows  
We can have simultaneously Linux and Windows on the machine using [WSL - Windows Subsystem for Linux](https://github.com/CRUSTDE-ContainerizedRustDevEnv/win10_wsl2_debian11). It works fine for me.
- aad - android  
On my phone I have android. It will not matter for this project.
- aae - MacOS and iOS  
I will avoid doing anything directly on these OS.
- aaj - virtual machines  
OS can run on bare metal or inside a VM virtual machine. VM are great to isolate simpler things running on one beefy machine.
- aak - Linux containers  
Linux has [containers](https://github.com/CRUSTDE-ContainerizedRustDevEnv/crustde_cnt_img_pod) that are kind of small VM. It is not a perfect equivalent, but it is good for isolation, albeit not great. I know about Docker, but I choose to use the alternative Podman instead. I like to have my development environment inside a container [CRUSTDE](https://github.com/CRUSTDE-ContainerizedRustDevEnv).

### ab - networks

- aba - tcp, ip and udp  
The Internet protocol suite is the basis of internet communication. I will not use them directly.
- abb - web http request-response  
This protocol is simple to think about and strong enough for most of the internet. The client sends a request and the server reply with a response. Nothing more to see here.
- abc - websockets  
Finally there is a simultaneous two-way communication channel on the internet.
- abd - http2  
I don't know. I hope it is just an upgrade and it is backward compatible.
- abe - http3  
I don't know. I hope it is just an upgrade and it is backward compatible.
- abf - server-sent events  
SSE allows the server to push data to the client.
- abg - SSL, TLS and HTTPS  
This technology is securing the internet connection by encrypting data sent between a website and a browser.
- abj - ssh  
The SSH protocol is the standard way for remote work and file copy in Linux.

### ac - postgres database

- aca - database servers  
I run the Postgres server on Linux directly or in a container. The default port is 5432. In the container I use VSCode to forward the port 5432, so I can connect to the server from Windows.
- acb - database config
The initial databases of postgres are: postgres, template1 and template0. We should create a new database.
- acc - users and roles
The default admin user is called postgres. It is wise to create new users for different purposes. It is good to split the admin and normal user.
- acd - tables, fields, indexes

- ace - views, procedures, functions,...
- acf - administrative tools inside the database
- acg - database editor
For now I will use DBeaver on Windows, but I hope to find something else over time. I tried the VSCode extension, but it is not great.


### ad - Rust language

- ada - Rust language  
[Rust](https://www.rust-lang.org/) is a language empowering everyone to build reliable and efficient software. It is low level as C and does not have a garbage collector. It is striving to be safe against memory bugs.
- adb - rust compiler
Rustc is the rust frontend compiler. It uses LLVM for the backend compiler. I like to change the default linker to MOLD.
- adc - cargo crate dependencies  
Libraries for Rust are called crates. They are published on [crates.io](https://crates.io/). My personal problem is that I cannot trust these libraries. For one project I need hundreds of them and I just cannot trust them. But there is nothing I can do. It will be fine for hobby projects, but not for any production.
- add - other Rust tools  
They come along the installation like the linter Clippy or separately like cargo-auto.
- ade - cargo-auto  
All the actions we repeat as developers must be automated. I created the tool [automation_tasks_rs and cargo-auto](https://github.com/automation-tasks-rs) for that purpose.
- adf - cross platform compiling  
If needed Rust compiler on Linux can build an executable for Windows. That is nice.
- adi - development container crustde  
I like to have my development environment in a [Linux container CRUSTDE](https://github.com/CRUSTDE-ContainerizedRustDevEnv)
- adj - VSCode as Rust editor
VSCode is great. I like to use VSCode in Windows and remote connect to the Linux container CRUSTDE in Linux on WSL.
- adk - Rust analyzer  
rust-analyzer is an implementation of Language Server Protocol for the Rust programming language. It provides features like completion and goto definition for many code editors, including VS Code.
- adl - borrow checker  
Rust memory safety is achieved with these concepts: ownership, borrowing and lifetimes. It is a steep learning curve, but once you learn it, it becomes automatic to think with these concepts in mind.
- adm - expressions  
Rust is primarily an expression-based language. Nearly anything can return a value.
- adn - variable scope and shadowing  
Variable bindings have a scope, and are constrained to live in a block. A block is a collection of statements enclosed by braces {}. Shadowing is a strange, but useful concept. When we declare a new variable with the same name as a previous variable, the new variable shadows the previous variable. It is really useful, but I critique the choice of making it implicit and not explicit.

### af - AXUM web server

### ai - SSR server side rendering

### aj - client side rendering

### ak - WASM, javascript

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
