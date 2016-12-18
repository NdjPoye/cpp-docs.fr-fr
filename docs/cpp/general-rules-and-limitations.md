---
title: "R&#232;gles g&#233;n&#233;rales et limitations | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
ms.assetid: 6c48902d-4259-4761-95d4-e421d69aa050
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# R&#232;gles g&#233;n&#233;rales et limitations
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Section spécifique à Microsoft  
  
-   Si vous déclarez une fonction ou un objet sans l'attribut **dllimport** ou `dllexport`, la fonction ou l'objet n'est pas considéré comme une partie de l'interface DLL.  Par conséquent, la définition de la fonction ou de l'objet doit être présente dans ce module ou dans un autre module du même programme.  Pour que la fonction ou que l'objet fasse partie de l'interface DLL, vous devez déclarer la définition de la fonction ou de l'objet dans l'autre module en tant que `dllexport`.  Sinon, une erreur d'éditeur de liens est générée.  
  
     Si vous déclarez une fonction ou un objet avec l'attribut `dllexport`, sa définition doit apparaître dans un module du même programme.  Sinon, une erreur d'éditeur de liens est générée.  
  
-   Si un seul module de votre programme contient **dllimport** et des déclarations `dllexport` pour la même fonction ou pour le même objet, l'attribut `dllexport` est prioritaire sur l'attribut **dllimport**.  Toutefois, un avertissement du compilateur est généré.  Par exemple :  
  
    ```  
    __declspec( dllimport ) int i;  
    __declspec( dllexport ) int i;   // Warning; inconsistent;  
                                     // dllexport takes precedence.  
    ```  
  
-   En C\+\+, vous pouvez initialiser un pointeur données local déclaré globalement ou statique avec l'adresse d'un objet de données déclaré avec l'attribut **dllimport**, ce qui génère une erreur en C.  Vous pouvez également initialiser un pointeur fonction local statique avec l'adresse d'une fonction déclarée avec l'attribut **dllimport**.  En C, ce type d'assignation définit le pointeur sur l'adresse de la conversion de code d'importation de la DLL \(stub de code qui transfère un contrôle à la fonction\) plutôt que l'adresse de la fonction.  En C\+\+, il définit le pointeur sur l'adresse de la fonction.  Par exemple :  
  
    ```  
    __declspec( dllimport ) void func1( void );  
    __declspec( dllimport ) int i;  
  
    int *pi = &i;                             // Error in C  
    static void ( *pf )( void ) = &func1;     // Address of thunk in C,  
                                              // function in C++  
  
    void func2()  
    {  
       static int *pi = &i;                  // Error in C  
       static void ( *pf )( void ) = &func1; // Address of thunk in C,  
                                             // function in C++  
    }  
    ```  
  
     Toutefois, comme un programme qui inclut l'attribut `dllexport` dans la déclaration d'un objet doit fournir la définition de cet objet dans le programme, vous pouvez initialiser un pointeur fonction statique global ou local avec l'adresse d'une fonction `dllexport`.  De même, vous pouvez initialiser un pointeur de données statiques global ou local avec l'adresse d'un objet de données `dllexport`.  Par exemple, le code suivant ne génère pas d'erreur en C ni en C\+\+ :  
  
    ```  
    __declspec( dllexport ) void func1( void );  
    __declspec( dllexport ) int i;  
  
    int *pi = &i;                              // Okay  
    static void ( *pf )( void ) = &func1;      // Okay  
  
    void func2()  
    {  
        static int *pi = &i;                   // Okay  
        static void ( *pf )( void ) = &func1;  // Okay  
    }  
    ```  
  
-   Suite à une modification du comportement apportée dans Visual C\+\+ .NET pour rendre l'application de `dllexport` plus cohérente entre les classes normales et les spécialisations de modèles de classe, si vous appliquez `dllexport` à une classe normale qui possède une classe de base qui n'est pas marquée comme `dllexport`, le compilateur génère une erreur C4275.  
  
     Le compilateur génère le même avertissement si la classe de base est une spécialisation d'un modèle de classe.  Pour contourner ce problème, marquez la classe de base avec `dllexport`.  Le problème avec une spécialisation d'un modèle de classe est l'emplacement de **\_\_declspec\(dllexport\)** ; vous n'êtes pas autorisé à marquer le modèle de classe.  Au lieu de cela, instanciez le modèle de classe et marquez cette instanciation explicite avec `dllexport`.  Par exemple :  
  
    ```  
    template class __declspec(dllexport) B<int>;  
    class __declspec(dllexport) D : public B<int> {  
    // ...  
    ```  
  
     Cette solution de contournement échoue si l'argument template est la classe dérivée.  Par exemple :  
  
    ```  
    class __declspec(dllexport) D : public B<D> {  
    // ...  
    ```  
  
     Étant donné qu'il s'agit du modèle commun avec les modèles, le compilateur a modifié la sémantique de `dllexport` lorsqu'il est appliqué à une classe qui comporte une ou plusieurs classes de base et qu'une ou plusieurs classes de base sont une spécialisation d'un modèle de classe.  Dans ce cas, le compilateur applique implicitement `dllexport` aux spécialisations des modèles de classe.  Dans Visual C\+\+ .NET, un utilisateur peut procéder comme suit pour ne pas obtenir d'avertissement :  
  
    ```  
    class __declspec(dllexport) D : public B<D> {  
    // ...  
    ```  
  
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [dllexport, dllimport](../cpp/dllexport-dllimport.md)