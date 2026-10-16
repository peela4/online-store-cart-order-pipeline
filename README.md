#online store cart order pipeline
A Java-based online store project for managing shopping carts and processing customer orders.
import java.util.Arraylist;
import java.util.Scanner;
class Product{
int id;
String name;
double price;
product(int id ,String name ,double price ){
this id=id;
this name=name;
this price=price;
}
void displayProduct(){
System.out.println(id+"."+name+"."+price);
}

class cart {
 ArrayList<Product>product = new ArrayList<>();
 void addproduct(Product p) {
 products.add (p);
 System.out.println("Product added to cart")
 }
void displayCart() {
if (products.isEmpty()) {
System.out.println("Cart is empty.");
return;
}
System.out.println("\n--- Your Cart ---");
for (Product p : products) {
p.displayProduct();
}
}
double calculateTotal() {
        double total = 0;

        for (Product p : products) {
            total = total + p.price;
        }

        return total;
    }

    void placeOrder() {
        if (products.isEmpty()) {
            System.out.println("Cart is empty. Add products first.");
            return;
        }

        System.out.println("\n--- Order Summary ---");
        displayCart();

        System.out.println("Total Amount: Rs." + calculateTotal());
        System.out.println("Order placed successfully!");
        System.out.println("Order confirmed. Thank you for shopping!");

        products.clear();
    }
}

public class OnlineStore {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Cart cart = new Cart();

        Product p1 = new Product(1, "Laptop", 45000);
        Product p2 = new Product(2, "Headphones", 1500);
        Product p3 = new Product(3, "Mouse", 500);

        int choice;

        do {
            System.out.println("\n--- ONLINE STORE ---");
            System.out.println("1. Display Products");
            System.out.println("2. Add Product to Cart");
            System.out.println("3. Display Cart");
            System.out.println("4. Calculate Total");
            System.out.println("5. Place Order");
            System.out.println("6. Exit");
            System.out.print("Enter your choice: ");

            choice = sc.nextInt();

            switch (choice) {
                case 1:
                    p1.displayProduct();
                    p2.displayProduct();
                    p3.displayProduct();
                    break;

                case 2:
                    System.out.print("Enter product ID (1-3): ");
                    int id = sc.nextInt();

                    if (id == 1) {
                        cart.addProduct(p1);
                    } else if (id == 2) {
                        cart.addProduct(p2);
                    } else if (id == 3) {
                        cart.addProduct(p3);
                    } else {
                        System.out.println("Invalid product ID.");
                    }
                    break;

                case 3:
                    cart.displayCart();
                    break;

                case 4:
                    System.out.println("Total Amount: Rs."
                            + cart.calculateTotal());
                    break;

                case 5:
                    cart.placeOrder();
                    break;

                case 6:
                    System.out.println("Thank you for visiting!");
                    break;

                default:
                    System.out.println("Invalid choice.");
            }

        } while (choice != 6);

        sc.close();
    }
}
