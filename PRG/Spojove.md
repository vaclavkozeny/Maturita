# Spojové struktury

`Spojové struktury, seznamy, stromy`

## Spojové struktury

- prvky nejsou za sebou v paměti
- obsahují odkaz na následující prvek
- mají kořen (počáteční prvek)

## Linked List (Spojový seznam)

- jednosměrný list, jehož prvky odkazují na následující prvek
- časová složitost:
  - najdi prvek: O(n)
  - přidej prvek na začátek: O(1)
  - přidej prvek někam: O(n)
  - smaž prvek: O(n)

```CSharp
class Node{
    public int data;
    public Node next;
}
class LinkedList{
    public Node head;
    public LinkedList(){
        head = null;
    }
}
```

<image src="./images/LL.png">

### Dvojitý spojový seznam

- má odkaz na předchozí a následující prvek

```CSharp
class Node{
    public int data;
    public Node next;
    public Node previous;
}
class LinkedList{
    public Node head;
    public LinkedList(){
        head = null;
    }
}
```

### Kruhová spojový seznam

- poslední prvek odkazuje na první

<image src="./images/kl.png">

## Tree

- větvené struktury
- obsahují kořen, uzle a listy

```CSharp
class Node{
    public int data;
    public Node[] subTrees;
}
class Tree{
    public Node root;
    public Tree(){
        root = null;
    }
}
```

<image src="./images/tree.png">

### Binary Tree

- každý prvek(Parent) obsahuje 0, 1 nebo 2 následující prvky(Child)

```CSharp
class Node{
    public int data;
    public Node leftChild;
    public Node rightChild;
}
class BinTree{
    public Node root;
    public BinTree(){
        root = null;
    }
}
```

- **Binary search tree** je velmi podobná struktura
- platí pravidlo: `LeftChild < Parent < RightChild`

### Procházení stromu

<image src="./images/search.png">

### Heap

- halda (heap)
- vyvážený binární strom

<image src="./images/heap.png">

## Graf

- struktura složená z uzlů (Node) a hran (Edge)
- každý uzel může mít libovolný počet sousedních uzlů

<image src="./images/faktnevim.webp">
