package foodordersystem;
import java.url.ArrayList;
import java.url.List;
import java.url.Scanner;
public class FoodOrderSystem {
 static class FoodItem {
 String name;
 double price;
 FoodItem(String name, double price) {
 this.name = name;
 this.price = price;
 }
 public String toString() {
 return name + " - $" + String.format("%.2f", 
price);
 }
 }
static class FoodOffer {
 String description;
 double discount;
FoodOffer(String description, double discount) {
 this.description = description;
 this.discount = discount;
 }
 }
public static void main (String [] args) {
 List<FoodItem> menu = List.of(
 new FoodItem("Burger", 5.99),
 new FoodItem("Pizza", 8.99),
 new FoodItem("Salad", 4.99),
new FoodItem("Soda", 1.99),
new FoodItem("Fries", 2.99)
);
List<FoodOffer> offers = List.of(
new FoodOffer("Discount on total order", 2.00),
new FoodOffer("Free soda with every order 
above $20", 1.99)
 );
List<FoodItem> order = new ArrayList<>();
Scanner scanner = new Scanner (System.in);
System.out.println("Welcome to the Food 
Ordering System!");
 System.out.println("Please select items from 
the menu:");
 for (int i = 0; i < menu.size(); i++) {
System.out.print("%d. %s%n", i + 1,
menu.get(i));
 }
while (true) {
 System.out.print("Enter item number to 
order (or type 'done' to finish): ");
 String input = scanner.nextLine();
 if (input.equalsIgnoreCase("done"))
break;
try {
 int itemNumber = Integer.parseInt(input);
 if (itemNumber > 0 && itemNumber <= 
menu.size()) {
order.add(menu.get(itemNumber - 1));
System.out.println("Added " +
menu.get(itemNumber - 1).name + " to your 
order.");
} 
else {
System.out.println("Invalid item number. Please 
try again.");
}
} 
catch (NumberFormatException e) {
 System.out.println("Invalid input. Please 
enter a number or 'done'.");
 }
 }
double totalCost = 
order.stream().mapToDouble(item -> 
item.price).sum();
 if (totalCost > 20) {
 for (FoodOffer offer : offers) {
 
 if (offer.description.equals("Free soda with every 
order above $20")) {
 
 totalCost -= offer.discount;
 System.out.println("Applied offer: " + 
offer.description);
 }
 }
 }
 System.out.println("Your order summary:");
 order.forEach(item -> System.out.println("- " + 
item));
System.out.print("Total cost after offers: 
$%.2f%n", totalCost);
scanner.close(); 
}
}


