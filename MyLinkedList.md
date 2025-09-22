# MyLinkedList

    public class MyLinkedList<A> {
    
        private class Node {
            public A element;
            public Node next;
    
            public Node(A element) {
                this.element = element;
                this.next = null;
            }
    
            public Node(A element, Node next) {
                this.element = element;
                this.next = next;
            }
        }
    
        private Node head;
        private int size;
    
        public MyLinkedList() {
            this.head = null;
            this.size = 0;
        }
    
        private Node getNode(int index) {
            if (index < 0 || index >= size) {
                throw new IndexOutOfBoundsException();
            }
            Node current = head;
            for (int i = 0; i < index; i++) {
                current = current.next;
            }
            return current;
        }
    
        public void addLast(A element) {
            Node node = new Node(element);
            Node current = this.head;
            if (current == null) {
                this.head = node;
                this.size = 1;
            } else {
                while (current.next != null) {
                    current = current.next;
                }
                current.next = node;
                this.size++;
            }
        }
    
        public void add(int index, A element) {
            if (index == 0) {
                Node node = new Node(element);
                node.next = this.head;
                this.head = node;
            } else {
                Node current = getNode(index - 1);
                current.next = new Node(element, current.next);
            }
            this.size++;
        }
    
        public A get(int index) {
            Node current = getNode(index);
            return current.element;
        }
    
        public void removeLast() {
            Node current = this.head;
            Node temp = this.head;
            while (current.next != null) {
                temp = current;
                current = current.next;
            }
            current = temp;
            current.next = null;
        }
    }
