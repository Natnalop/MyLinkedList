# Main
    public class Main {
        public static void main(String[] args) {
            MyLinkedList<Integer> list = new MyLinkedList<>();
            list.addLast(198);
            list.addLast(12);
    
            list.get(1);
            list.get(0);
    
            list.add(2, 18);
            list.add(3, 87);
    
            list.removeLast();
        }
    }
