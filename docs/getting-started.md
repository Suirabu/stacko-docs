# Getting Started

## Download Stacko

To begin using Stacko you'll first need to clone it from the [official repository](https://github.com/Mercifle/Stacko).

```bash
git clone https://github.com/Mercifle/Stacko.git
```

Enter the newly created `Stacko` directory and run the interpreter using Python3.

```bash
cd Stacko
python3 Stacko.py
```

## Install the Interpreter

To use the Stacko interpreter from anywhere in your system you'll first need to install it locally.

To begin you'll first need to make the Stacko interpreter executable. To do this, run the following command from within
the Stacko directory.

```bash
chmod +x Stacko.py
```

Next add a link to the interpreter to your local `bin` directory.

```bash
ln Stacko.py /usr/local/bin/stacko
```

Now, try running the Stacko interpreter from anywhere in your system using the following command.

```bash
stacko
```

You may need to add `/usr/local/bin/` to your path if it is not already included there. This can be done temporarily
with the following command.

```bash
export PATH=$PATH:/usr/local/bin
```

Using this method your local `bin` directory will remain in your path until you close your current bash session.

To make this change permanent simply add the previous command to your `.bashrc` with the following command.

```bash
echo "export PATH=$PATH:/usr/local/bin" >> ~/.bashrc
```

## Run a Script

Let's create and run a simple "Hello, world!" program using Stacko!

The begin, create a new file with either the `.stko` or the `.stacko` file extension. So long as the file uses either
of the previously listed file extensions a Stacko script can be given any name. For this example we'll name our file
`HelloWorld.stacko`.

```bash
touch HelloWorld.stacko
```

Open your newly created file and enter the following code.

```py
# Write "Hello, world!" to stdout
"Hello, world!" printLine
```

You can run this script using the following command.

```bash
stacko HelloWorld.stacko
```

Congratulations, you've just successfully written and ran your first Stacko script!
