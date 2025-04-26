# Grocery-Store
# using python


class GroceryStore: 
    def __init__(self): 
        self.inventory = { 
            "Apple": {"price": 2, "stock": 50}, 
            "Banana": {"price": 1, "stock": 100}, 
            "Milk": {"price": 3, "stock": 30}, 
            "Bread": {"price": 2, "stock": 40} 
        } 
        self.cart = {} 
 
    def display_items(self): 
        print("\nAvailable Items:") 
        for item, details in self.inventory.items(): 
            print(f"{item}: ${details['price']} | Stock: {details['stock']}") 
 
    def add_to_cart(self, item, quantity): 
        if item in self.inventory and self.inventory[item]['stock'] >= quantity: 
            if item in self.cart: 
                self.cart[item] += quantity 
            else: 
                self.cart[item] = quantity 
            self.inventory[item]['stock'] -= quantity 
            print(f"{quantity} {item}(s) added to cart.") 
        else: 
            print("Item not available or insufficient stock.") 
 
    def remove_from_cart(self, item, quantity): 
        if item in self.cart and self.cart[item] >= quantity: 
            self.cart[item] -= quantity 
            self.inventory[item]['stock'] += quantity 
if self.cart[item] == 0: 
del self.cart[item] 
print(f"{quantity} {item}(s) removed from cart.") 
else: 
print("Item not in cart or invalid quantity.") 
def checkout(self): 
total = 0 
print("\nYour Cart:") 
for item, quantity in self.cart.items(): 
price = self.inventory[item]['price'] * quantity 
print(f"{item}: {quantity} x ${self.inventory[item]['price']} = ${price}") 
total += price 
print(f"Total Bill: ${total}") 
self.cart.clear() 
print("Thank you for shopping with us!") 
# Main Program 
grocery_store = GroceryStore() 
while True: 
print("\n1. View Items\n2. Add to Cart\n3. Remove from Cart\n4. Checkout\n5. Exit") 
choice = input("Enter your choice: ") 
if choice == "1": 
grocery_store.display_items() 
elif choice == "2": 
item = input("Enter item name: ") 
quantity = int(input("Enter quantity: ")) 
grocery_store.add_to_cart(item, quantity) 
elif choice == "3": 
item = input("Enter item name: ") 
quantity = int(input("Enter quantity: ")) 
grocery_store.remove_from_cart(item, quantity) 
elif choice == "4": 
grocery_store.checkout() 
elif choice == "5": 
print("Exiting... Have a great day!") 
break 
else: 
print("Invalid choice. Try again.") 
