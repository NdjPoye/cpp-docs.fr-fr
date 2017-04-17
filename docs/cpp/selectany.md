---
title: "selectany | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "selectany_cpp"
  - "selectany"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec (mot clé) (C++), selectany"
  - "selectany __declspec (mot clé)"
ms.assetid: 9c353017-5a42-4f50-b741-bd13da1ce84d
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# selectany
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Indique au compilateur que l'élément de données global déclaré \(variable ou objet\) est un COMDAT pick\-any \(une fonction packagée\).  
  
## Syntaxe  
  
```  
  
__declspec( selectany ) declarator  
```  
  
## Notes  
 Au moment d'effectuer le lien, si plusieurs définitions d'un COMDAT s'affichent, l'éditeur de liens en choisit un et ignore le reste.  Si l'option de l'éditeur de liens [\/OPT:REF](../build/reference/opt-optimizations.md) \(optimisations\) est sélectionnée, l'élimination COMDAT se produit pour supprimer tous les éléments de données non référencés dans la sortie de l'Éditeur de liens.  
  
 Les constructeurs et l'assignation par fonction globale ou méthodes statiques dans la déclaration ne créent pas de référence et n'empêchent pas la suppression \/OPT:REF.  Les effets secondaires d'un tel code ne doivent pas créer de dépendances quand il n'existe aucune autre référence à des données.  
  
 Pour les objets dynamiquement initialisés et globaux, `selectany` ignorera le code d'initialisation d'un objet non référencé, également.  
  
 Un élément de données global ne peut généralement être initialisé qu'une seule fois dans un projet EXE ou DLL.  `selectany` peut être utilisé en initialisant les données globales définies par les en\-têtes, lorsque le même en\-tête apparaît dans plusieurs fichiers source.  `selectany` est disponible dans les compilateurs C et C\+\+.  
  
> [!NOTE]
>  `selectany` peut être appliqué à l'initialisation actuelle des éléments de données globaux qui sont visibles.  
  
## Exemple  
 Ce code indique comment utiliser l'attribut `selectany` :  
  
```  
//Correct - x1 is initialized and externally visible   
__declspec(selectany) int x1=1;  
  
//Incorrect - const is by default static in C++, so   
//x2 is not visible externally (This is OK in C, since  
//const is not by default static in C)  
const __declspec(selectany) int x2 =2;  
  
//Correct - x3 is extern const, so externally visible  
extern const __declspec(selectany) int x3=3;  
  
//Correct - x4 is extern const, so it is externally visible  
extern const int x4;  
const __declspec(selectany) int x4=4;  
  
//Incorrect - __declspec(selectany) is applied to the uninitialized  
//declaration of x5  
extern __declspec(selectany) int x5;  
  
// OK: dynamic initialization of global object  
class X {  
public:  
X(int i){i++;};  
int i;  
};  
  
__declspec(selectany) X x(1);  
```  
  
## Exemple  
 Ce code indique comment utiliser l'attribut `selectany` pour garantir le repli des données COMDAT lorsque vous utilisez également l'option de l'éditeur de liens pour [\/OPT:ICF](../build/reference/opt-optimizations.md).  Notez que les données doivent être marquées avec `selectany` et être placées dans une section **const** \(lecture seule\).  Vous devez spécifier explicitement la section en lecture seule.  
  
```  
// selectany2.cpp  
// in the following lines, const marks the variables as read only  
__declspec(selectany) extern const int ix = 5;  
__declspec(selectany) extern const int jx = 5;  
int main() {  
   int ij;  
   ij = ix + jx;  
}  
```  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_\_declspec](../cpp/declspec.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)