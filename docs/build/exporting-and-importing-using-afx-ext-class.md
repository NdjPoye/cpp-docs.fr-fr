---
title: "Exportation et importation &#224; l&#39;aide de AFX_EXT_CLASS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "afx_ext_class"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AFX_EXT_CLASS (macro)"
  - "fichiers exécutables (C++), importer des classes"
  - "exporter des classes (C++)"
  - "exporter des DLL (C++), AFX_EXT_CLASS (macro)"
  - "DLL d'extension (C++), exporter des classes"
  - "importer des DLL (C++)"
ms.assetid: 6b72cb2b-e92e-4ecd-bcab-c335e1d1cfde
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Exportation et importation &#224; l&#39;aide de AFX_EXT_CLASS
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les [DLL d'extension](../build/extension-dlls-overview.md) utilisent la macro **AFX\_EXT\_CLASS** pour exporter des classes ; les exécutables qui sont liés à la DLL d'extension utilisent cette macro pour importer des classes.  La macro **AFX\_EXT\_CLASS** vous permet de réutiliser avec les exécutables liés à la DLL les fichiers d'en\-tête que vous avez utilisés pour générer la DLL d'extension.  
  
 Dans le fichier d'en\-tête de la DLL, ajoutez le mot clé **AFX\_EXT\_CLASS** à la déclaration de votre classe, de la manière suivante :  
  
```  
class AFX_EXT_CLASS CMyClass : public CDocument  
{  
// <body of class>  
};  
```  
  
 Cette macro est définie par les MFC en tant que **\_\_declspec\(dllexport\)** lorsque les symboles de préprocesseur **\_AFXDLL** et `_AFXEXT` sont définis.  Mais la macro est définie en tant que **\_\_declspec\(dllimport\)** quand le symbole **\_AFXDLL** est défini et que le symbole `_AFXEXT` n'est pas défini.  Lorsqu'il est défini, le symbole de préprocesseur **\_AFXDLL** indique que la version partagée des MFC est utilisée par l'exécutable cible \(une DLL ou une application\).  Quand **\_AFXDLL** et `_AFXEXT` sont tous deux définis, l'exécutable cible est une DLL d'extension.  
  
 Comme **AFX\_EXT\_CLASS** est définie en tant que **\_\_declspec\(dllexport\)** lors d'une exportation à partir d'une DLL d'extension, vous pouvez exporter des classes entières sans placer les noms décorés de tous les symboles de cette classe dans le fichier .def.  Cette méthode est utilisée par l'exemple MFC [DLLHUSK](http://msdn.microsoft.com/fr-fr/dfcaa6ff-b8e2-4efd-8100-ee3650071f90).  
  
 Bien que vous puissiez éviter de créer un fichier .def et tous les noms décorés de la classe avec cette méthode, il est plus efficace de créer un fichier .def, car les noms peuvent être exportés par ordinal.  Pour utiliser la méthode d'exportation par fichier .def, placez le code suivant au début et à la fin du fichier d'en\-tête :  
  
```  
#undef AFX_DATA  
#define AFX_DATA AFX_EXT_DATA  
// <body of your header file>  
#undef AFX_DATA  
#define AFX_DATA  
```  
  
> [!CAUTION]
>  Soyez vigilant lorsque vous exportez des fonctions inline, car elles peuvent donner lieu à des conflits de versions.  Une fonction inline est développée en code d'application ; par conséquent, si vous réécrivez la fonction par la suite, celle\-ci n'est mise à jour que si l'application elle\-même est recompilée.  En principe, les fonctions de la DLL peuvent être mises à jour sans régénération des applications qui les utilisent.  
  
## Exportation de membres individuels d'une classe  
 Vous souhaiterez peut\-être parfois exporter des membres individuels de votre classe.  Par exemple, si vous exportez une classe dérivée de `CDialog`, il se peut que vous n'ayez à exporter que le constructeur et l'appel à `DoModal`.  Vous pouvez appliquer **AFX\_EXT\_CLASS** aux différents membres à exporter.  
  
 Par exemple :  
  
```  
class CExampleDialog : public CDialog  
{  
public:  
   AFX_EXT_CLASS CExampleDialog();  
   AFX_EXT_CLASS int DoModal();  
   ...  
   // rest of class definition  
   ...  
};  
```  
  
 Comme vous n'exportez plus tous les membres de la classe, vous risquez de rencontrer un autre problème en raison du mode de fonctionnement des macros MFC.  Plusieurs des macros d'assistance des MFC déclarent ou définissent en fait des données membres.  Par conséquent, ces données membres doivent également être exportées à partir de la DLL.  
  
 Par exemple, la macro `DECLARE_DYNAMIC` est définie de la façon suivante lors de la génération d'une DLL d'extension :  
  
```  
#define DECLARE_DYNAMIC(class_name) \  
protected: \  
   static CRuntimeClass* PASCAL _GetBaseClass(); \  
public: \  
   static AFX_DATA CRuntimeClass class##class_name; \  
   virtual CRuntimeClass* GetRuntimeClass() const; \  
```  
  
 La ligne commençant par le modificateur `AFX_DATA` statique déclare un objet statique à l'intérieur de la classe.  Pour exporter cette classe correctement et accéder aux informations d'exécution à partir d'un exécutable client, vous devez exporter cet objet statique.  Dans la mesure où l'objet statique est déclaré avec le modificateur `AFX_DATA`, vous devez définir `AFX_DATA` en tant que **\_\_declspec\(dllexport\)** seulement lors de la génération de la DLL et le définir en tant que **\_\_declspec\(dllimport\)** lors de la génération de l'exécutable client.  Comme **AFX\_EXT\_CLASS** est déjà définie de cette façon, il vous suffit de redéfinir `AFX_DATA` pour lui donner la même valeur que **AFX\_EXT\_CLASS** autour de la définition de votre classe.  
  
 Par exemple :  
  
```  
#undef  AFX_DATA  
#define AFX_DATA AFX_EXT_CLASS  
  
class CExampleView : public CView  
{  
   DECLARE_DYNAMIC()  
   // ... class definition ...  
};  
  
#undef  AFX_DATA  
#define AFX_DATA  
```  
  
 Comme les MFC utilisent toujours le symbole `AFX_DATA` sur les éléments de données qu'elles définissent dans leurs macros, cette technique fonctionne pour tous les scénarios de ce type.  Par exemple, elle fonctionne pour `DECLARE_MESSAGE_MAP`.  
  
> [!NOTE]
>  Si vous exportez la classe entière plutôt qu'une sélection de membres de la classe, les données membres statiques sont exportées automatiquement  
  
### Que voulez\-vous faire ?  
  
-   [Exporter à partir d'une DLL à l'aide de fichiers .def](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Exporter à partir d'une DLL à l'aide de \_\_declspec\(dllexport\)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Exporter des fonctions C\+\+ à utiliser dans des exécutables en langage C](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Exporter des fonctions C à utiliser dans des exécutables en langage C ou C\+\+](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [Déterminer la méthode d'exportation à utiliser](../build/determining-which-exporting-method-to-use.md)  
  
-   [Importer dans une application à l'aide de \_\_declspec\(dllimport\)](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [Initialiser une DLL](../build/initializing-a-dll.md)  
  
### Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Noms décorés](../build/reference/decorated-names.md)  
  
-   [Importation et exportation de fonctions inline](../build/importing-and-exporting-inline-functions.md)  
  
-   [Importations mutuelles](../build/mutual-imports.md)  
  
## Voir aussi  
 [Exportation à partir d'une DLL](../build/exporting-from-a-dll.md)