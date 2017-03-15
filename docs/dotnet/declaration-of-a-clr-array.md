---
title: "D&#233;claration d&#39;un tableau CLR | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "array (mot clé C++)"
ms.assetid: 36a8883c-2663-43f0-a90c-28f27035e036
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# D&#233;claration d&#39;un tableau CLR
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La syntaxe servant à déclarer, instancier et initialiser un tableau managé a été modifiée entre Extensions managées pour C\+\+ et [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  
  
 La déclaration d'un objet tableau CLR en Extensions managées était une extension de la déclaration de tableau standard dans laquelle un mot clé `__gc` se trouvait placé entre le nom de l'objet tableau et sa dimension éventuellement remplie de virgules, comme dans les deux exemples suivants :  
  
```  
void PrintValues( Object* myArr __gc[]);  
void PrintValues( int myArr __gc[,,]);  
```  
  
 Cette opération a été simplifiée dans la nouvelle syntaxe, où nous utilisons une déclaration de type modèle, qui suggère la déclaration STL `vector`.  Le premier paramètre indique le type d'élément.  Le deuxième paramètre spécifie la dimension du tableau \(avec une valeur par défaut de 1, si bien que seules les dimensions multiples nécessitent un deuxième argument\).  L'objet tableau lui\-même est un handle de suivi et doit donc recevoir un chapeau.  Si le type d'élément est également un type référence, il requiert un chapeau.  Par exemple, l'exemple précédent, exprimé dans la nouvelle syntaxe, donne :  
  
```  
void PrintValues( array<Object^>^ myArr );  
void PrintValues( array<int,3>^ myArr );  
```  
  
 Puisqu'un type référence est un handle de suivi plutôt qu'un objet, il est possible de spécifier un tableau CLR comme étant le type de retour d'une fonction. \(Par contraste, il n'est pas possible de spécifier le tableau natif comme type de retour d'une fonction.\) La syntaxe nécessaire en Extensions managées n'était pas assez intuitive.  Par exemple :  
  
```  
Int32 f() [];  
int GetArray() __gc[];  
```  
  
 Dans [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)], la déclaration est beaucoup plus simple.  Par exemple :  
  
```  
array<Int32>^ f();  
array<int>^ GetArray();  
```  
  
 L'initialisation abrégée d'un tableau managé local est prise en charge par les deux versions du langage.  Par exemple :  
  
```  
int GetArray() __gc[] {  
   int a1 __gc[] = { 1, 2, 3, 4, 5 };  
   Object* myObjArray __gc[] = {   
      __box(26), __box(27), __box(28), __box(29), __box(30)  
   };  
   return a1;  
}  
```  
  
 est considérablement simplifié dans la nouvelle syntaxe \(notez que la conversion boxing étant implicite dans la nouvelle syntaxe, l'opérateur `__box` a été éliminé \- voir [Types valeur et leurs comportements \(C\+\+\/CLI\)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)\) :  
  
```  
array<int>^ GetArray() {  
   array<int>^ a1 = {1,2,3,4,5};  
   array<Object^>^ myObjArray = {26,27,28,29,30};  
   return a1;  
}  
```  
  
 Un tableau étant un type référence CLR, la déclaration de chaque objet tableau est un handle de suivi.  Les objets tableau doivent donc être alloués sur le tas CLR. \(La notation abrégée masque l'allocation de tas managée.\) Voici la forme explicite d'une initialisation d'objet tableau sous Extensions managées :  
  
```  
Object* myArray[] = new Object*[2];  
String* myMat[,] = new String*[4,4];  
```  
  
 Dans la nouvelle syntaxe, l'expression `new` est remplacée par `gcnew`.  Les tailles de dimensions sont passées en tant que paramètres à l'expression `gcnew`, comme suit :  
  
```  
array<Object^>^ myArray = gcnew array<Object^>(2);  
array<String^,2>^ myMat = gcnew array<String^,2>(4,4);  
```  
  
 Dans la nouvelle syntaxe, une liste d'initialisation explicite peut suivre l'expression `gcnew`, ce qui n'était pas pris en charge dans les Extensions managées.  Par exemple :  
  
```  
// explicit initialization list following gcnew   
// was not supported in Managed Extensions  
array<Object^>^ myArray =   
   gcnew array<Object^>(4){ 1, 1, 2, 3 };  
```  
  
## Voir aussi  
 [Types managés \(C\+\+\/CL\)](../dotnet/managed-types-cpp-cl.md)   
 [Arrays](../windows/arrays-cpp-component-extensions.md)