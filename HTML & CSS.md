***
```
/**
 * The LinkedStacj class represents a Stack of either String of Integer items.
 */
public class LinkedStakc {
    private int N;
    private Node first;
    private String stringOrInt;

    // helper linked list class
    private class Node {
        private String itemifString;
        private int itemIfInteger;
        private Node next;
    }

    /**
     * Initializes an empty Stack.
     * @param StringOrInt "String" if wanting a stack of Strings, "Integer" if
     * wanting a stack of Integers
     */
    public LinkedStack(String StringOrInt) {
        first = null;
        N = 0;
        stringOrInt = StringOrInt;
    }

    /**
     * Is this Stack empty?
     * @return true if this Stack is empty; false otherwise
     */
    public boolean isEmpty() {
        return size() == 0;
    }

    /**
     * Returns the number of items in the Stack.
     * @return the number of items in the Stack
     */
    public int size() {
        int numberOfNodes = 0;
        for (; first != null; first = first.next, numberOfNodes++) {}
        return numberOfNodes;
    }

    /**
     * Adds the item to this Stack.
     * @param item the item to add
     */
    public void push(Object item) {
        Node oldfirst = first;
        first = new Node();
        N++;

        if (stringOrInt.equals("String")) {
            first.itemifString = (String) item;
        } else if (stringOrInt.equals("Integer")) {
            first.itemIfInteger = (Integer) item;
        } else {
            throw new IllegalArgumentException("Invalid type");
        }

        first.next = oldfirst;
    }

    /**
     * Removes and returns the item most recently added to this Stack.
     * @return the item most recently added
     */
    public Object pop() {
        N--;
        String itemToReturnIfString = null;
        int itemToReturnIfInteger = null;

        if (stringOrInt == "String")
            itemToReturnIfString = first.itemifString;
            first = first.next;
        else if (stringOrInt.equals("Integer"))
            itemToReturnIfInteger = first.itemIfInteger;
            first = first.next; // delete first node

        if (stringOrInt.equals("String"))
            return (Object) itemToReturnIfString;
        else
            return (Object) itemToReturnIfInteger;
    }

    /**
     * Returns index of item if found, otherwise returns -1
     */
    public int search(Object item) {
        int i = 0;
        if(stringOrInt == "string") {
            String itemStr = (String) item;
            while(itemStr != first.itemifString) {
                first = first.next;
                i++;
            }
            if((first.itemifString == itemStr) {
                return i;
            }
        }
        else if (stringOrInt.equals("integer")) {
            Integer ItemInt = (Integer) item;
            int i = 0;
            while(ItemInt != first.itemIfInteger) {
                first = first.next;
                i++;
            }
            if((first.itemIfInteger == ItemInt) {
                return i;
            }
        }
        return i;
    }

}
```