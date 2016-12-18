---
title: "Importations mutuelles | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "symbole du préprocesseur _AFXEXT"
  - "AFX_DATA"
  - "AFX_EXT_CLASS (macro)"
  - "importations circulaires"
  - "DLL (C++), importer"
  - "fichiers exécutables (C++), importer"
  - "exporter des DLL (C++), importations mutuelles"
  - "DLL d'extension (C++), importations mutuelles"
  - "importer des DLL (C++), importations mutuelles"
  - "importations de DLL mutuelles (C++)"
  - "importer mutuellement des fichiers exécutables (C++)"
ms.assetid: 2cc29537-92ee-4d92-af39-8b8b3afd808f
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Importations mutuelles
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'exportation ou l'importation vers un autre fichier exécutable présente des complications quand les importations sont mutuelles \(ou circulaires\).  Par exemple, deux DLL importent des symboles l'une de l'autre, à l'instar des fonctions mutuelles récurrentes.  
  
 Le problème que posent les fichiers exécutables effectuant une importation mutuelle \(généralement des DLL\) est qu'il est impossible de générer l'un sans générer l'autre d'abord.  Chaque processus de génération requiert une entrée, une bibliothèque d'importation produite par l'autre processus de génération.  
  
 La solution consiste à utiliser l'utilitaire LIB avec l'option \/DEF, qui produit une bibliothèque d'importation sans générer le fichier exécutable.  Grâce à cet utilitaire, vous pouvez générer toutes les bibliothèques d'importation dont vous avez besoin, quel que soit le nombre de DLL impliquées et le degré de complexité des dépendances.  
  
 Pour gérer les importations mutuelles, la solution générale à adopter est la suivante :  
  
1.  Traitez chaque DLL à tour de rôle. \(L'ordre peut être quelconque, mais certains ordres permettent une meilleure optimisation.\) Si toutes les bibliothèques d'importation nécessaires existent et sont en cours, exécutez LINK pour générer le fichier exécutable \(DLL\).  La bibliothèque d'importation est ainsi générée.  Sinon, exécutez LIB pour produire une bibliothèque d'importation.  
  
     L'exécution de LIB avec l'option \/DEF génère un fichier supplémentaire doté de l'extension .EXP.  Le fichier .EXP doit être utilisé ultérieurement pour générer le fichier exécutable.  
  
2.  Après avoir utilisé LINK ou LIB pour générer toutes les bibliothèques d'importation, faites marche arrière et exécutez LINK pour générer les fichiers exécutables qui n'ont pas été générés au cours de l'étape précédente.  Notez que le fichier .exp correspondant doit être spécifié sur la ligne LINK.  
  
     Si vous aviez exécuté l'utilitaire LIB plus tôt pour générer une bibliothèque d'importation pour DLL1, LIB aurait également généré le fichier DLL1.exp.  Vous pouvez utiliser DLL1.exp comme entrée de LINK lors de la génération de DLL1.exp.  
  
 L'illustration suivante affiche une solution pour deux DLL qui s'importent mutuellement, DLL1 et DLL2.  Dans l'étape 1, vous devez exécuter LIB, avec l'option \/DEF définie, sur DLL1.  L'étape 1 génère DLL1.lib, une bibliothèque d'importation, et DLL1.exp.  Dans l'étape 2, la bibliothèque d'importation est utilisée pour générer DLL2, laquelle à son tour produit une bibliothèque d'importation pour les symboles de DLL2.  L'étape 3 génère DLL1, en utilisant DLL1.exp et DLL2.lib comme entrée.  Notez qu'un fichier .EXP pour DLL2 n'est pas nécessaire, car LIB n'était pas utilisée pour générer la bibliothèque d'importation de DLL2.  
  
 ![Utilisation d'importations mutuelles pour lier deux DLL](../build/media/vc37yj1.png "vc37YJ1")  
Liaison de deux DLL avec des importations mutuelles  
  
## Limitations de \_AFXEXT  
 Vous pouvez utiliser le symbole de préprocesseur `_AFXEXT` pour des DLL d'extension du moment que vous n'avez pas plusieurs couches de DLL d'extension.  Si vous avez des DLL d'extension qui appellent ou dérivent des classes dans vos propres DLL d'extension, lesquelles dérivent ensuite de classes MFC, vous devez utiliser votre propre symbole de préprocesseur pour éviter toute ambiguïté.  
  
 Le problème est que dans Win32, vous devez déclarer de manière explicite toutes les données en tant que **\_\_declspec\(dllexport\)** si l'exportation s'effectue à partir d'une DLL, et en tant que **\_\_declspec\(dllimport\)** si l'importation a lieu à partir d'une DLL.  Lorsque vous définissez `_AFXEXT`, les en\-têtes MFC doivent s'assurer que le symbole **AFX\_EXT\_CLASS** est défini correctement.  
  
 Lorsque vous avez plusieurs couches, un symbole tel que **AFX\_EXT\_CLASS** n'est pas suffisant, dans la mesure où une DLL d'extension peut exporter de nouvelles classes, mais aussi importer d'autres classes d'une autre DLL d'extension.  Pour résoudre ce problème, utilisez un symbole de préprocesseur spécial qui indique que vous n'êtes pas en train d'utiliser la DLL, mais plutôt de la générer.  Par exemple, imaginez deux DLL d'extension, A.dll et B.dll.  Elles exportent chacune certaines classes dans A.h et B.h, respectivement.  B.dll utilise les classes dans A.dll.  Les fichiers d'en\-tête ressembleraient à ce qui suit :  
  
```  
/* A.H */  
#ifdef A_IMPL  
   #define CLASS_DECL_A   __declspec(dllexport)  
#else  
   #define CLASS_DECL_A   __declspec(dllimport)  
#endif  
  
class CLASS_DECL_A CExampleA : public CObject  
{ ... class definition ... };  
  
// B.H  
#ifdef B_IMPL  
   #define CLASS_DECL_B   __declspec(dllexport)  
#else  
   #define CLASS_DECL_B   __declspec(dllimport)  
#endif  
  
class CLASS_DECL_B CExampleB : public CExampleA  
{ ... class definition ... };  
...  
```  
  
 Lorsque A.dll est générée, elle est générée avec `/D A_IMPL` et lorsque B.dll est générée, elle est générée avec `/D B_IMPL`.  En utilisant des symboles séparés pour chaque DLL, `CExampleB` est exporté et `CExampleA` est importé lors de la génération de B.dll.  `CExampleA` est exporté lors de la génération d'A.dll et importé s'il est utilisé par B.dll \(ou un autre client\).  
  
 Cette superposition en couches ne peut être effectuée lorsque vous utilisez les symboles du préprocesseur intégrés **AFX\_EXT\_CLASS** et `_AFXEXT`.  La technique décrite ci\-dessus corrige ce problème d'une manière qui n'est pas sans rappeler celle que le mécanisme des MFC applique pour générer des DLL d'extension de type technologies actives, base de données et réseau.  
  
## Non\-exportation de la classe entière  
 Lorsque vous n'exportez pas une classe entière, vous devez vous assurer que les éléments de données nécessaires créés par les macros MFC sont exportés correctement.  Vous pouvez réaliser cette opération en redéfinissant `AFX_DATA` en fonction de la macro de votre classe spécifique.  Vous devez accomplir cette tâche lorsque vous n'exportez pas la classe entière.  
  
 Par exemple :  
  
```  
/* A.H */  
#ifdef A_IMPL  
   #define CLASS_DECL_A  _declspec(dllexport)  
#else  
   #define CLASS_DECL_A  _declspec(dllimport)  
#endif  
  
#undef  AFX_DATA  
#define AFX_DATA CLASS_DECL_A  
  
class CExampleA : public CObject  
{  
   DECLARE_DYNAMIC()  
   CLASS_DECL_A int SomeFunction();  
   //... class definition ...  
};  
  
#undef AFX_DATA  
#define AFX_DATA  
```  
  
### Que voulez\-vous faire ?  
  
-   [Exporter à partir d'une DLL](../build/exporting-from-a-dll.md)  
  
-   [Exporter à partir d'une DLL à l'aide de fichiers .DEF](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Exporter à partir d'une DLL à l'aide de \_\_declspec\(dllexport\)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Exporter et importer à l'aide de AFX\_EXT\_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [Exporter des fonctions C\+\+ à utiliser dans des exécutables en langage C](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Déterminer la méthode d'exportation à utiliser](../build/determining-which-exporting-method-to-use.md)  
  
-   [Importer dans une application à l'aide de \_\_declspec\(dllimport\)](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
### Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Utilitaire LIB et option \/DEF](../build/reference/lib-reference.md)  
  
## Voir aussi  
 [Importation et exportation](../build/importing-and-exporting.md)