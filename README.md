class Product:
    def __init__(self, product_id, product_name, price):
        self.product_id = product_id
        self.product_name = product_name
        self.price = price

    def display_product(self):
        print(f"ID: {self.product_id}, Name: {self.product_name}, Price: ₹{self.price}")


class ShoppingCart:
    def __init__(self):
        self.cart_items = []

    def add_item(self, product):
        self.cart_items.append(product)
        print(f"{product.product_name} added to cart.")

    def remove_item(self, product_id):
        for product in self.cart_items:
            if product.product_id == product_id:
                self.cart_items.remove(product)
                print(f"{product.product_name} removed from cart.")
                return
        print("Product not found in cart.")

    def view_cart(self):
        if len(self.cart_items) == 0:
            print("Cart is empty.")
        else:
            print("\nCart Items:")
            for product in self.cart_items:
                product.display_product()

    def calculate_total(self):
        total = 0
        for product in self.cart_items:
            total += product.price
        print(f"\nTotal Bill Amount: ₹{total}")


# Creating Products
product1 = Product(101, "Laptop", 50000)
product2 = Product(102, "Mobile", 20000)
product3 = Product(103, "Headphones", 3000)

# Creating Shopping Cart
cart = ShoppingCart()

# Display Products
print("Available Products:")
product1.display_product()
product2.display_product()
product3.display_product()

# Add Items
cart.add_item(product1)
cart.add_item(product2)
cart.add_item(product3)

# View Cart
cart.view_cart()

# Remove Item
cart.remove_item(102)

# View Updated Cart
cart.view_cart()

# Calculate Total
cart.calculate_total()
