<h1> Chapter 1 </h1>
"A -> B -> C" := this is a function that takes two arguments of types "A" and "B" and returns a value of type "C".

- Function calls are generally postfix; i.e. func arg1 arg2 instead of func(arg1,arg2)
    - Parantheses can be used in function call for passing a sub-expression; i.e foo arg1 (fun arg2)
    - When using operators those are infix; i.e. 1 + 1

`Guard Syntax`
```haskell
sign :: Int -> Int
sign n
    | n < 0 = (-1)
    | n == 0 = 0
    | otherwise = 1
```

Idea: Exhaustively map function behavior, n will return on the first evaluted line that is true. Executed top to bottom.

`Let-in vs where for function sub-expressions`
```haskell
sumLast2 :: Integer -> Integer
sumLast2 n = lastDigit n + secondLastDigit n
  where
    lastDigit :: Integer -> Integer
    lastDigit x = mod x 10
    secondLastDigit :: Integer -> Integer
    secondLastDigit x = mod (div x 10) 10

sumLast2LetIn :: Integer -> Integer
sumLast2LetIn n =
    let lastDigit = mod n 10
        secondLastDigit = mod (div n 10) 10
    in lastDigit + secondLastDigit
```

Recursion is the same as imperative languages
```haskell
firstDigit :: Integer -> Integer
firstDigit n = if n < 10 then n else firstDigit (div n 10)
```

<h1> Chapter 2 </h1>

List type is generically expressed as [a]. I.E. [True, True] :: [Bool]. Also, String <=> [Char].

Variables in haskell are immutable so applying a function to a variable returns a new instance.

Adding elements to the head of the list is cheap in haskell since they are implemented as linked lists/cons lists.

**LEFT OFF AT PATTERN MATCHING**