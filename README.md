#online store cart order pipeline
A Java-based online store project for managing shopping carts and processing customer orders.
import java.util.Arrayslist;
import java.util.Scanner;
class product{
int id=
string name;
double price;
product(int id ;string name ;double price )
this id=id;
this name=name;
this price=price;
}
void displayproduct(){
system.out.println(id+"."+name+"."+price);
}

class cart {
 ArrayList<Product>Product = new ArrayList<>();
 void addproduct(Product p) {
 products add (p);
 System.out.println("Product added to cart")
 }
void displayCart() {
if (products.isEmpty()) {
System.out.println("Cart is empty.");
return;{
}
System.out.println("\n--- Your Cart ---");
for (Product p : products) {
p.displayProduct();
}
}
