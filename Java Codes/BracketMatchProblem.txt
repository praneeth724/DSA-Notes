import java.util.*;
public class BrMatch {
    Stack<Character> stack = new Stack<>();

    public void match(char arr[]){
        char element;
        char popedElement;
        for(int i =0; i < arr.length; i++){
            element = arr[i];

            if(element == '{' || element == '(' || element == '['){
                stack.push(element);
                continue;
            }

            switch (element) {
                case '}':
                    popedElement = stack.pop();
                    if(popedElement == '(' || popedElement == '['){
                        System.out.println("False");
                        return;
                    }
                    break;
                case ']':
                    popedElement = stack.pop();
                    if(popedElement == '(' || popedElement == '{'){
                        System.out.println("False");
                        return;
                    }
                    break;
                case ')':
                    popedElement = stack.pop();
                    if(popedElement == '{' || popedElement == '['){
                        System.out.println("False");
                        return;
                    }
                    break;
            }
        }
        System.out.println("True");
    }
}