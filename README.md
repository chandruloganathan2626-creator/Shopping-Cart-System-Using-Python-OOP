# Shopping-Cart-System-Using-Python-OOP
Developed a Python-based Shopping Cart System using Object-Oriented Programming (OOP). The application allows users to add products, remove items, view cart details, and calculate the total bill. Implemented classes, objects, attributes, and methods to build a simple and efficient shopping management system.

class Product:

    def __init__(self, id, name, price):
        self.id = id
        self.name = name
        self.price = price

    def show(self):
        print(self.id, self.name, self.price)


class ShoppingCart:

    def __init__(self):
        self.cart = []

    def add(self, product):
        self.cart.append(product)
        print("Product added")

    def remove(self, id):

        for product in self.cart:
            if product.id == id:
                self.cart.remove(product)
                print("Product removed")
                return

        print("Product not found")

    def show_cart(self):

        if not self.cart:
            print("Cart is empty")
        else:
            for product in self.cart:
                print(product.id, product.name, product.price)

    def total(self):

        total = 0

        for product in self.cart:
            total += product.price

        print("Total =", total)


# Products

p1 = Product(1, "Laptop", 50000)
p2 = Product(2, "Mouse", 800)
p3 = Product(3, "Keyboard", 1500)


products = [p1, p2, p3]

cart = ShoppingCart()


# Menu

while True:

    print("\n1. Products")
    print("2. Add")
    print("3. Remove")
    print("4. Cart")
    print("5. Total")
    print("6. Exit")

    choice = input("Enter choice: ")

    if choice == "1":

        for product in products:
            product.show()

    elif choice == "2":

        id = int(input("Enter product ID: "))

        for product in products:
            if product.id == id:
                cart.add(product)
                break

    elif choice == "3":

        id = int(input("Enter product ID: "))
        cart.remove(id)

    elif choice == "4":

        cart.show_cart()

    elif choice == "5":

        cart.total()

    elif choice == "6":

        print("Thank you")
        break

    else:
        print("Invalid choice")
