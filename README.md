# Evaluate-Reverse-Polish-Notation

class Solution:
    def evalRPN(self, tokens: List[str]) -> int:
        stack=[]
        str1='+-*/'
        for i in tokens:
            if i in str1:
                b=stack.pop()
                a=stack.pop()
                if i == "+":
                    stack.append(a+b)
                elif i == "-":
                    stack.append(a-b)
                elif i == "*":
                    stack.append(a*b)
                else:
                    stack.append(int(a/b))
            else:
                stack.append(int(i))
        return stack.pop()
