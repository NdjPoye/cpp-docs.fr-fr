---
title: "TN033&#160;: version DLL de MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.dll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AFXDLL (bibliothèque)"
  - "version DLL de MFC (C++)"
  - "DLL (C++), MFC"
  - "DLL MFC (C++), écrire des DLL d'extension"
  - "TN033"
ms.assetid: b6f1080b-b66b-4b1e-8fb1-926c5816392c
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN033&#160;: version DLL de MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette note explique comment utiliser les bibliothèques de liens dynamiques partagées MFCxx.dll et MFCxxD.dll \(où x est le numéro de version MFC\) avec les applications MFC et les DLL d'extension.  Pour plus d'informations sur les DLL standard, consultez l'[Utilisation de MFC dans le cadre d'une DLL](../mfc/tn011-using-mfc-as-part-of-a-dll.md).  
  
 Cette note technique traite les aspects des DLL.  Les deux derniers sont destinés à des utilisateurs expérimentés :  
  
-   [Comment générer une DLL d'extension de MFC](#_mfcnotes_how_to_write_an_mfc_extension_dll)  
  
-   [Comment vous créez une application de MFC utilisant la version de DLL de MFC](#_mfcnotes_writing_an_application_that_uses_the_dll_version)  
  
-   [Comment les bibliothèques MFC partagées de liens dynamiques sont implémentées](#_mfcnotes_how_the_mfc30.dll_is_implemented)  
  
 Si vous vous désirez créer par MFC une DLL qui peut être utilisé avec les applications non\-MFC \(cela s'appelle une DLL standard\), reportez\-vous à [Note technique 11](../mfc/tn011-using-mfc-as-part-of-a-dll.md).  
  
## Vue d'ensemble de la prise en charge de MFCxx.DLL : Terminologie et fichiers  
 **Regular DLL**: Utilisez une DLL standard pour générer une DLL autonome à l'aide de certaines des classes de MFC.  Les interfaces à la limite App\/DLL sont des interfaces « C», et l'application cliente ne doit pas nécessairement être une application de MFC.  
  
 Ceci est la version du support des DLL qui fonctionne avec MFC 1.0.  Il est décrit dans la [Note technique 11](../mfc/tn011-using-mfc-as-part-of-a-dll.md) et les concepts avancés par MFC échantillonnent [DLLScreenCap](../top/visual-cpp-samples.md).  
  
> [!NOTE]
>  À compter de la version 4,0 de Visual C\+\+, le terme **USRDLL** est obsolète et a été remplacé par une DLL standard qui lie statiquement à MFC.  Vous pouvez également générer une DLL standard qui lie dynamiquement à MFC.  
  
 MFC 3,0 \(et versions ultérieures\) prend en charge les DLL standard avec toutes les nouvelles fonctionnalités, OLE et les classes de base de données inclus.  
  
 **AFXDLL**: On s'y réfère également comme étant la version partagée des bibliothèques MFC.  Il s'agit de la prise en charge de la DLL ajoutée dans MFC 2,0.  La bibliothèque MFC est elle\-même dans plusieurs DLL \(décrits ci\-dessous\) et une application cliente ou une DLL lie dynamiquement les DLL dont elle a besoin.  Les interfaces de la limite application\/DLL sont des interfaces de la classe de C\+\+\/MFC.  L'application cliente DOIT être une application de MFC.  Il prend en charge toutes les fonctionnalités de MFC 3,0 \(exception : UNICODE n'est pas prise en charge pour les classes de base de données\).  
  
> [!NOTE]
>  À compter de la version 4,0 de Visual C\+\+, ce type de DLL s'appelle un « DLL d'extension ».  
  
 Cette note utilisera MFCxx.DLL pour faire référence à l'intégralité de la DLL MFC, notamment :  
  
-   Débogage : MFCxxD.DLL \(combinées\) et MFCSxxD.LIB \(statique\).  
  
-   Version : MFCxx.DLL \(combinées\) et MFCSxx.LIB \(statique\).  
  
-   Débogage Unicode : MFCxxUD.DLL \(combinées\) et MFCSxxD.LIB \(statique\).  
  
-   Version Unicode : MFCxxU.DLL \(combinées\) et MFCSxxU.LIB \(statique\).  
  
> [!NOTE]
>  Les bibliothèques de MFCSxx\[U\]\[D\].LIB sont utilisées conjointement aux DLL partagées MFC.  Ces librairies contiennent du code qui doit être lié statiquement à l'application ou la DLL.  
  
 Une application lie vers des bibliothèques d'importation correspondantes :  
  
-   Débogage : MFCxxD.LIB  
  
-   Version : MFCxx.LIB  
  
-   Débogage Unicode : MFCxxUD.LIB  
  
-   Version Unicode : MFCxxU.LIB  
  
 « Une DLL d'extension de MFC » est une DLL généré sur MFCxx.DLL \(et\/ou les autres DLL partagées MFC\).  C'est ici que le composant d'architecture MFC entre en jeu.  Si vous dérivez une classe utile d'une classe de MFC, ou générez un autre toolkit sous forme de MFC, vous pouvez le placer dans la DLL.  Cette DLL utilise MFCxx.DLL, de même que l'application cliente finale.  Cela permet d'avoir des classes réutilisables de feuille, de classes de base, ainsi que de vue\/document.  
  
## Les pour et les contre  
 Pourquoi devriez\-vous utiliser la version partagée de MFC ?  
  
-   Utiliser la bibliothèque partagée peut résulter en de plus petites applications \(une application minimale qui utilise la majorité de la bibliothèque MFC est inférieure à 10K\).  
  
-   La version partagée de DLL d'extension de MFC de prises en charge MFC et les DLL standard.  
  
-   Générer une application qui utilise les bibliothèques MFC partagées est plus rapide que de générer une application statiquement liée de MFC car il n'est pas nécessaire de lier MFC lui\-même.  Cela est particulièrement vrai dans les versions de **DÉBOGUER** où l'éditeur de liens doit compacter les informations de débogage — en liant avec une DLL qui contient déjà les informations de débogage, il y a moins d'informations de débogage à compacter dans votre application.  
  
 Pourquoi vous ne devriez pas utiliser la version partagée de MFC :  
  
-   Expédier une application qui utilise la bibliothèque partagée exige que vous expédiez la bibliothèque de MFCxx.DLL \(et d'autres\) avec votre programme.  MFCxx.DLL peut être redistribuées librement comme de nombreuses DLLs, mais vous devez toujours installer la DLL dans le programme d'installation.  De plus, vous devrez livrer MSVCRTxx.DLL, qui contient la bibliothèque Runtime C, laquelle est utilisée à la fois par votre programme et les DLL MFC elles\-mêmes.  
  
##  <a name="_mfcnotes_how_to_write_an_mfc_extension_dll"></a> Comment écrire une DLL d'extension MFC  
 Une DLL d'extension de MFC est une DLL qui contient des classes et des fonctions écrites pour embellir les fonctionnalités des classes de MFC.  Une DLL d'extension MFC utilise les DLLs partagée de MFC de la même façon qu'une application l'utilise, avec quelques remarques supplémentaires :  
  
-   Le processus de construction est semblable à générer une application qui utilise les bibliothèques MFC partagées avec quelques compilateurs et options de l'éditeur de liens supplémentaires.  
  
-   Une DLL d'extension de MFC n'a pas de classe dérivée `CWinApp`.  
  
-   Une DLL d'extension de MFC doit fournir un `DllMain` spécial.  AppWizard fournit une fonction de `DllMain` que vous pouvez modifier.  
  
-   Une DLL d'extension de MFC fournit généralement une routine d'initialisation pour créer une **CDynLinkLibrary** si la DLL d'extension souhaite exporter des `CRuntimeClass` ou des ressources à l'application.  Une classe dérivée de **CDynLinkLibrary** peut être utilisée si les données par application doivent être gérées par la DLL de l'extension.  
  
 Ces règles sont décrites de manière plus détaillée ci\-dessous.  Vous devez également faire référence à l'exemple des concepts avancés de MFC, [DLLHUSK](../top/visual-cpp-samples.md), étant donné qu'il montre :  
  
-   Créer une application à l'aide de bibliothèques partagées. \(DLLHUSK.EXE est une application de MFC qui lie dynamique des bibliothèques MFC ainsi que d'autres DLL\).  
  
-   Générer une DLL d'extension de MFC. \(Notez les indicateurs spéciaux tels qu' `_AFXEXT` qui sont utilisées pour générer une DLL d'extension\)  
  
-   Deux exemples de DLL d'extension de MFC.  L'un présente la structure de base d'une DLL d'extension de MFC avec des opérations limitées \(TESTDLL1\) et l'autre montre l'exportation d'une interface de la classe entière \(TESTDLL2\).  
  
 L'application cliente et toutes les DLLs d'extension doivent utiliser la même version de MFCxx.DLL.  Vous devez suivre la convention de la DLL MFC et fournir un débogage et la version de vente au détail \(\/release\) de la DLL d'extension.  Cela permet aux programmes clients de générer le débogage et les versions de ventes de leurs applications et de les lier avec le débogage approprié ou la version commerciale de toutes les DLL.  
  
> [!NOTE]
>  Vu les problèmes d'exportation et d'amputation des noms du C\+\+, la liste d'exportation à partir d'une DLL d'extension peut varier entre la version Debug et la version commerciale pour la même DLL et les DLL de plateformes différentes.  La MFCxx.DLL commerciale compte près de 2000 points d'entrée exportés, alors que la MFCxxD.DLL de débogage en possède près de 3000.  
  
### Remarque rapide sur la gestion de la mémoire  
 La section intitulée « gestion de la mémoire, » vers la fin de cette note technique, décrit l'implémentation du MFCxx.DLL avec la version partagée de MFC.  Les informations que vous devez connaître pour implémenter un seul DLL d'extension sont décrites ici.  
  
 MFCxx.DLL et toutes les DLL d'extension chargées dans l'espace d'adressage d'une application cliente utiliseront les mêmes modules d'allocation de mémoire, de chargement de ressources et autres états "globaux" MFC que si elles faisaient partie de la même application.  Ceci est important car les bibliothèques des DLL non\-MFC et les DLL normales qui se lient statiquement à MFC font exactement le contraire et s'assurent que chaque DLL affecte une partie de son propre pool de mémoires.  
  
 Si une DLL d'extension alloue de la mémoire, alors cette mémoire peut alors être librement mélangée avec tout autre objet alloué par l'application.  De même, si une application qui utilise les bibliothèques partagées MFC s'arrête, la protection du système d'exploitation assurera l'intégrité de toute autre application MFC partageant la DLL.  
  
 D'autres états MFC "globaux", comme le fichier exécutable en cours à partir duquel il faut charger des ressources, sont également partagés entre l'application cliente et toutes les DLL d'extension MFC ainsi que MFCx0.dll elle\-même.  
  
### Générer une DLL d'extension de MFC  
 Vous pouvez utiliser AppWizard pour créer un projet de DLL d'extension de MFC, et il génèrera automatiquement les paramètres pertinents du compilateur et de l'éditeur de liens.  Il génèrera également une fonction de `DllMain` que vous pouvez modifier.  
  
 Si vous convertissez un projet existant en une DLL d'extension de MFC, commencez par les règles standard pour générer une application qui utilise la version partagée de MFC, puis procédez comme suit :  
  
-   Ajoutez **\/D\_AFXEXT** aux indicateurs de compilateur.  Dans la boîte de dialogue de propriétés du projet, sélectionnez le nœud C\/C\+\+.  Sélectionnez la catégorie du préprocesseur.  Ajoutez `_AFXEXT` aux champ de définition des Macros, en séparant chacun des éléments avec des points\-virgules.  
  
-   Supprimez le commutateur de compilation de **\/Gy**.  Dans la boîte de dialogue de propriétés du projet, sélectionnez le nœud C\/C\+\+.  Sélectionnez la catégorie de génération de code.  Vérifiez que l'option « activer la liaison au niveaux des fonctions » n'est pas activé.  Cela simplifiera pour exporter des classes car l'éditeur de liens ne supprime pas les fonctions non référencée.  Si le projet d'origine est utilisé pour générer une DLL normale statiquement liée à MFC, modifiez l'option du compilateur de **\/MT\[d\]** à **\/MD\[d\]**.  
  
-   Générez une bibliothèque d'exportation à l'aide de l'option **\/DLL** pour LIER.  Cela sera défini lorsque vous créerez une nouvelle cible, en spécifiant la bibliothèque de liens dynamiques Win32 comme type de cible.  
  
### Modifier les fichiers d'en\-tête  
 L'objectif d'une DLL d'extension est généralement d'exporter certaines fonctionnalités communes à une ou plusieurs applications qui peuvent utiliser cette fonctionnalité.  Ceci revient à exporter les classes et les fonctions globales disponibles pour les applications clientes.  
  
 Pour effectuer cette opération vous devez vous assurer que chacune des fonctions membres est marquée comme importation ou exportation selon ce qui est approprié.  Cela implique des déclarations spéciales : **\_\_declspec\(dllexport\)** et **\_\_declspec\(dllimport\)**.  Lorsque vos classes sont utilisées par les applications clientes, il faudra les déclarer comme **\_\_declspec\(dllimport\)**.  Lorsque la DLL d'extension elle\-même est générée, elles doivent être déclarées comme **\_\_declspec\(dllexport\)**.  En outre, les fonctions doivent être exportées de fait, afin que les programmes clients se lient à elle au moment du chargement.  
  
 Pour exporter votre classe entière, utilisez **AFX\_EXT\_CLASS** dans la définition de classe.  La macro est définie par l'infrastructure comme **\_\_declspec\(dllexport\)** lorsque **\_AFXDLL** et `_AFXEXT` est défini, mais est définie comme **\_\_declspec\(dllimport\)** lorsque `_AFXEXT` n'est pas définie.  `_AFXEXT` comme décrit ci\-dessus, est défini uniquement lorsque vous générez la DLL d'extension.  Par exemple :  
  
```  
class AFX_EXT_CLASS CExampleExport : public CObject  
{ ... class definition ... };  
```  
  
### Non\-exportation de la classe entière  
 Parfois vous pouvez exporter immédiatement les membres nécessaires de la classe.  Par exemple, si vous exportez une classe dérivée de `CDialog`, il se peut que vous n'ayez à exporter que le constructeur et l'appel à `DoModal`.  Vous pouvez exporter les membres à l'aide du fichier .DEF de la DLL, mais vous pouvez également utiliser **AFX\_EXT\_CLASS** à peu près de la même manière sur les membres que vous devez exporter.  
  
 Par exemple :  
  
```  
class CExampleDialog : public CDialog  
{  
public:  
   AFX_EXT_CLASS CExampleDialog();  
   AFX_EXT_CLASS int DoModal();  
   // rest of class definition  
   .  
   .  
   .  
};  
```  
  
 Comme vous n'exportez plus tous les membres de la classe, vous risquez de rencontrer un autre problème en raison du mode de fonctionnement des macros MFC.  Le problème est dans la façon dont les macros MFC fonctionnent.  Plusieurs des macros d'assistance des MFC déclarent ou définissent en fait des données membres.  Par conséquent, ces données membres doivent également être exportées à partir de la DLL.  
  
 Par exemple, la macro `DECLARE_DYNAMIC` est définie de la façon suivante lors de la génération d'une DLL d'extension :  
  
```  
#define DECLARE_DYNAMIC(class_name) \  
protected: \  
   static CRuntimeClass* PASCAL _GetBaseClass(); \  
   public: \  
   static AFX_DATA CRuntimeClass class##class_name; \  
   virtual CRuntimeClass* GetRuntimeClass() const; \  
```  
  
 La ligne commençant par le modificateur "`AFX_DATA` statique" déclare un objet statique à l'intérieur de la classe.  Pour exporter cette classe correctement et accéder aux informations d'exécution à partir d'un exécutable client, vous devrez exporter cet objet statique.  Dans la mesure où l'objet statique est déclaré avec le modificateur `AFX_DATA`, vous devez définir `AFX_DATA` en tant que **\_\_declspec\(dllexport\)** seulement lors de la génération de la DLL et le définir en tant que **\_\_declspec\(dllimport\)** lors de la génération de l'exécutable client.  
  
 Comme discuté ci\-dessus, **AFX\_EXT\_CLASS** est déjà défini de cette façon.  Vous devez simplement redéfinir `AFX_DATA` pour être identique à **AFX\_EXT\_CLASS** autour de votre définition de classe.  
  
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
  
 Comme les MFC utilisent toujours le symbole `AFX_DATA` sur les éléments de données qu'elles définissent dans leurs macros, cette technique fonctionnera pour tous les scénarios de ce type.  Par exemple, elle fonctionnera pour `DECLARE_MESSAGE_MAP`.  
  
> [!NOTE]
>  Si vous exportez la classe entière plutôt qu'une sélection de membres de la classe, les données membres statiques sont exportées automatiquement  
  
 Vous pouvez utiliser la même technique pour exporter automatiquement l'opérateur d'analyse `CArchive` pour les classes qui utilisent des macros `DECLARE_SERIAL` et `IMPLEMENT_SERIAL`.  Exporter l'opérateur d'archive en retirant la déclaration de classe \(trouvent dans. Fichier de H\) avec le code suivant :  
  
```  
#undef AFX_API  
#define AFX_API AFX_EXT_CLASS  
  
<your class declarations here>  
  
#undef AFX_API  
#define AFX_API  
```  
  
### Limitations de \_AFXEXT  
 Vous pouvez utiliser le symbole de préprocesseur**AFXEXT** pour des DLL d'extension du moment tant que vous n'avez pas plusieurs couches de DLL d'extension.  Si vous avez des DLL d'extension qui appellent ou dérivent des classes dans vos propres DLL d'extension, lesquelles dérivent ensuite de classes MFC, vous devez utiliser votre propre symbole de préprocesseur pour éviter toute ambiguïté.  
  
 Le problème est que dans Win32, vous devez déclarer de manière explicite toutes les données en tant que **\_\_declspec\(dllexport\)** si l'exportation s'effectue à partir d'une DLL, et en tant que **\_\_declspec\(dllimport\)** si l'importation a lieu à partir d'une DLL.  Lorsque vous définissez `_AFXEXT`, les en\-têtes MFC doivent s'assurer que le symbole **AFX\_EXT\_CLASS** est défini correctement.  
  
 Lorsque vous avez plusieurs couches, un symbole tel que **AFX\_EXT\_CLASS** n'est pas suffisant, dans la mesure où une DLL d'extension peut éventuellement exporter de nouvelles classes, mais aussi importer d'autres classes d'une autre DLL d'extension.  De façon à résoudre ce problème, utilisez un symbole de préprocesseur spécial qui indique que vous n'êtes pas en train d'utiliser la DLL, mais plutôt de la générer.  Par exemple, imaginez deux DLL d'extension, A.DLL et B.DLL.  Elles exportent chacune certaines classes dans A.H et B.H, respectivement.  B.DLL utilise les classes dans A.DLL.  Les fichiers d'en\-tête ressembleraient à ce qui suit :  
  
```  
/* A.H */  
#ifdef A_IMPL  
   #define CLASS_DECL_A   __declspec(dllexport)  
#else  
   #define CLASS_DECL_A   __declspec(dllimport)  
#endif  
  
class CLASS_DECL_A CExampleA : public CObject  
{ ... class definition ... };  
  
/* B.H */  
#ifdef B_IMPL  
   #define CLASS_DECL_B   __declspec(dllexport)  
#else  
   #define CLASS_DECL_B   __declspec(dllimport)  
#endif  
  
class CLASS_DECL_B CExampleB : public CExampleA  
{ ... class definition .. };  
```  
  
 Lorsque A.DLL est générée, elle est générée avec **\/D A\_IMPL** et lorsque B.dLL est générée, elle est générée avec **\/D B\_IMPL**.  En utilisant des symboles séparés pour chaque DLL, CExampleB est exporté et CExampleA est importé lors de la génération de B.dll.  CExampleA est exporté lors de la génération d'A.dll et importé s'il est utilisé par B.dll \(ou un autre client\).  
  
 Cette superposition en couches ne peut être effectuée lorsque vous utilisez les symboles du préprocesseur intégrés **AFX\_EXT\_CLASS**  et `_AFXEXT`.  La technique décrite ci\-dessus corrige ce problème d'une manière qui n'est pas sans rappeler celle que le mécanisme des MFC applique pour générer des DLL d'extension de type OLE, base de données et réseau.  
  
### Non\-exportation de la classe entière  
 De nouveau, vous devez faire attention particulière lorsque vous n'exportez pas une classe entière.  Vous devez vous assurer que les éléments de données nécessaires créées par les macros MFC sont exportées correctement.  Vous pouvez réaliser cette opération en redéfinissant **AFX\_DATA**  pour spécifier la macro de votre classe.  Vous devez accomplir cette tâche lorsque vous n'exportez pas la classe entière.  
  
 Par exemple :  
  
```  
// A.H  
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
   //class definition   
   .  
   .  
   .  
};  
  
#undef AFX_DATA  
#define AFX_DATA  
```  
  
### DllMain  
 Voici le code exact que vous devez placer dans votre fichier source principal de la DLL d'extension.  Il doit venir après la norme inclue.  Notez que lorsque vous utilisez AppWizard pour créer des fichiers de démarreur pour une DLL d'extension, il fournit `DllMain` automatiquement.  
  
```  
#include "afxdllx.h"  
  
static AFX_EXTENSION_MODULE extensionDLL;  
  
extern "C" int APIENTRY   
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID)  
{  
   if (dwReason == DLL_PROCESS_ATTACH)  
   {  
      // Extension DLL one-time initialization   
      if (!AfxInitExtensionModule(  
             extensionDLL, hInstance))  
         return 0;  
  
      // TODO: perform other initialization tasks here  
   }  
   else if (dwReason == DLL_PROCESS_DETACH)  
   {  
      // Extension DLL per-process termination  
      AfxTermExtensionModule(extensionDLL);  
  
          // TODO: perform other cleanup tasks here  
   }  
   return 1;   // ok  
}  
```  
  
 L'appel à `AfxInitExtensionModule` capture les classes d'exécution du module \(structures `CRuntimeClass`\)  ainsi que ses fabriques d'objets \(objets `COleObjectFactory`\) pour les utiliser lors de la création de l'objet  **CDynLinkLibrary**.  Cette fonction permet aux MFC de nettoyer la DLL d'extension chaque fois qu'un processus se détache de la DLL d'extension \(ce qui se produit lors de la sortie du processus ou quand la DLL est déchargée à la suite d'un appel à `AfxTermExtensionModule`\).  Comme la plupart des DLL d'extension ne sont pas chargés dynamiquement \(généralement, ils sont liés via les bibliothèques d'importation\), l'appel à `AfxTermExtensionModule` n'est généralement pas nécessaire.  
  
 Si votre application charge et libère les DLL d'extension dynamiquement, veillez à appeler `AfxTermExtensionModule` comme indiqué plus haut.  Veillez également à utiliser `AfxLoadLibrary` et `AfxFreeLibrary` \(au lieu de Win32 des fonctions **LoadLibrary** et **FreeLibrary**\) si votre application utilise des threads ou si elle charge dynamiquement une DLL d'extension.  L'utilisation de `AfxLoadLibrary` et de `AfxFreeLibrary` fait en sorte que le code de démarrage et d'arrêt qui s'exécute lors du chargement et du déchargement de la DLL d'extension n'altère pas l'état global des MFC.  
  
 Le fichier d'en\-tête AFXDLLX.H contient des définitions spéciales pour les structures utilisées dans les DLL d'extension, comme la définition de `AFX_EXTENSION_MODULE` et de **CDynLinkLibrary**.  
  
 L'*extensionDLL* global doit être déclarée comme indiqué.  A l'inverse de la version 16\-bits de MFC, vous pouvez allouer de la mémoire et faire appel à des fonctions MFC pendant ce temps, étant donné que MFCxx.DLL est complétement initialisée quand vous appelez `DllMain`.  
  
### Partage des ressources et des classes  
 Les DLL d'extension simples de MFC doivent uniquement exporter certaines fonctions à faible bande passante à l'application cliente et rien d'autre.  Plus de DLL d'interface utilisateur peuvent également vouloir exporter des ressources et les classes C\+\+ à l'application cliente.  
  
 L'exportation des ressources s'effectue par l'intermédiaire d'une liste de ressources.  Dans chaque application il y a une seule liste liée d'objets **CDynLinkLibrary**.  Lors de la recherche d'une ressource, la plupart des implémentations MFC standard qui chargent des ressources examinent d'abord le module de ressources en cours \(`AfxGetResourceHandle`\) et, si la ressource est introuvable, parcourent la liste des objets **CDynLinkLibrary** en vue d'essayer de charger la ressource demandée.  
  
 La création dynamique d'objets C\+\+ dotés d'un nom de classe C\+\+ est similaire.  Le mécanisme de désérialisation des objets MFC exige que tous les objets `CRuntimeClass` soient enregistrés afin qu'il puisse reconstruire en créant de manière dynamique l'objet C\+\+ du type requis sur la base de ce qui était stocké précédemment.  
  
 Si vous souhaitez que l'application cliente utilise les classes dans la DLL d'extension qui sont `DECLARE_SERIAL`, vous devez exporter vos classes soit visible dans l'application cliente.  Cela est également fait en parcourant la liste de **CDynLinkLibrary**.  
  
 Dans le cas de l'exemple des concepts avancés MFC [DLLHUSK](../top/visual-cpp-samples.md), la liste ressemble à ceci :  
  
```  
head ->   DLLHUSK.EXE   - or -   DLLHUSK.EXE  
               |                      |  
          TESTDLL2.DLL           TESTDLL2.DLL  
               |                      |  
          TESTDLL1.DLL           TESTDLL1.DLL  
               |                      |  
               |                      |  
            MFC90D.DLL            MFC90.DLL  
```  
  
 MFCxx.dll occupe généralement la dernière position sur la liste des ressources et des classes.  MFCxx.dll inclut toutes les ressources MFC standard, y compris les chaînes des invites de tous les ID de commande standard.  Le fait de la placer à la fin de la liste permet à toutes les DLL et à l'application cliente elle\-même de ne pas avoir leur propre copie des ressources MFC standard, mais de se fier plutôt aux ressources partagées dans la MFCxx.dll.  
  
 Le fait de fusionner les ressources et les noms de classes de toutes les DLL dans l'espace de noms de l'application cliente a pour inconvénient de vous obliger à être vigilant avec les ID ou les noms que vous sélectionnez.  Naturellement vous pouvez désactiver cette fonctionnalité en n'exportant pas soit vos ressources soit un objet de **CDynLinkLibrary** à l'application cliente.  L'exemple [DLLHUSK](../top/visual-cpp-samples.md) gère l'espace de noms des ressources partagées en utilisant plusieurs fichiers d'en\-tête.  Voir la [Note technique 35](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md) pour obtenir des conseils sur l'utilisation de fichiers de ressources partagées.  
  
### Initialisation de la DLL  
 Comme indiqué précédemment, vous souhaiterez généralement créer un objet de **CDynLinkLibrary** pour exporter vos ressources et les classes à l'application cliente.  Vous devez fournir un point d'entrée exporté pour initialiser la DLL.  Au minimum, il s'agit d'une routine void qui n'accepte aucun argument et retourne rien, mais ça peut être ce que vous le souhaitez.  
  
 Chaque application cliente qui veut utiliser la DLL doit appeler cette routine d'initialisation, si vous utilisez cette méthode.  Vous pouvez également allouer cet objet de **CDynLinkLibrary** dans votre `DllMain` juste après l'appel `AfxInitExtensionModule`.  
  
 La routine d'initialisation doit créer un objet de **CDynLinkLibrary** dans le segment d'application actuel, câblé jusqu'à vos informations de DLL d'extension.  Cela peut se faire avec ce qui suit :  
  
```  
extern "C" extern void WINAPI InitXxxDLL()  
{  
   new CDynLinkLibrary(extensionDLL);  
}  
```  
  
 Le nom actuel, *InitXxxDLL* dans cet exemple, peut être un nom de votre choix.  Il n'a pas besoin d'être `extern "C"`, mais cette opération permet de maintenir la liste d'exportation plus facilement.  
  
> [!NOTE]
>  Si vous utilisez la DLL de l'extension d'une DLL standard, vous devez exporter cette fonction d'initialisation.  Cette fonction doit être appelée de la DLL standard avant d'utiliser les classes ou ressources de la DLL d'extension.  
  
### Exporter des entrées  
 Le moyen simple d'exporter vos classes consiste à utiliser **\_\_declspec\(dllimport\)** et **\_\_declspec\(dllexport\)** sur chaque classe et fonction globale de votre choix à l'exportation.  Cela simplifie beaucoup la tâche, mais c'est moins efficace que de nommer chaque point d'entrée \(décrit ci\-dessous\) étant donné que vous avez moins de contrôle sur quelles fonctions vont être exportées et vous ne pouvez pas exporter les fonctions par leur numéro.  TESTDLL1 et TESTDLL2 utiliser cette méthode pour exporter ses entrées.  
  
 Une méthode plus efficace\(et la méthode utilisée par MFCxx.DLL\) consiste à exporter chaque entrée à la main lorsque vous nommez chaque entrée dans le fichier de .DEF.  Dans la mesure où nous exportons d'exportation sélectives de notre DLL \(autrement dit, pas toutes\), nous devons décider quelles interfaces particulières il souhaite à exporter.  Ceci est difficile puisque vous devez spécifier les noms tronquée à l'éditeur de liens sous la forme d'entrées dans le fichier de .DEF.  Ne pas exporter de classe C\+\+ sauf si vous devez réellement avoir un lien symbolique pour celles ci.  
  
 Si vous avez essayé d'exportation C\+\+ les classes ayant un .DEF fichier avant, vous pouvez développer un outil pour générer cette liste automatiquement.  Cela peut être accompli en utilisant un processus de lien en deux étapes.  Liez la DLL une fois sans exportation, puis activez l'éditeur de liens pour générer un fichier de .MAP.  Le fichier de .MAP permet de générer une liste de fonctions qui doivent être exportées, ce à réorganiser, il peut être utilisé pour générer les entrées EXPORT pour votre fichier de .DEF.  La liste d'exportation pour MFCxx.DLL et OLE et les DLL d'extension de base de données, au nombre de plusieurs milliers, a été générée avec ce processus \(bien qu'il n'est pas totalement automatique et ne requiert pas d'une main paramétrage occasionnellement\).  
  
### CWinApp et CDynLinkLibrary  
 Une DLL d'extension de MFC n'a pas d'objet `CWinApp` dérivé de lui même ; à la place il doit utiliser un objet `CWinApp` dérivé de l'application cliente.  Cela signifie que l'application cliente possède la pompe de messages principale, la boucle inactive etc.  
  
 Si la DLL d'extension MFC doit gérer des données supplémentaires pour chaque application, vous pouvez dériver une nouvelle classe à partir de **CDynLinkLibrary** et la créer dans la routine InitXxxDLL décrite plus haut.  Au moment de l'exécution, la DLL peut consulter la liste des objets **CDynLinkLibrary** de l'application en cours pour rechercher celui qui correspond à cette DLL d'extension particulière.  
  
### Utilisation des ressources dans votre implémentation de DLL  
 Comme indiqué précédemment, la charge par défaut des ressources parcourra la liste des objets de **CDynLinkLibrary** à la recherche du premier fichier EXE ou DLL qui contient la ressource demandée.  Les API ainsi que tous le code interne utilise `AfxFindResourceHandle` de MFC pour parcourir la liste des ressources pour rechercher une ressource, où qu'elle se situe.  
  
 Si vous souhaitez seulement charger les ressources à partir d'un emplacement spécifique, utilisez les API `AfxGetResourceHandle` et `AfxSetResourceHandle` pour enregistrer l'ancien handle et définir le nouveau handle.  Veillez à restaurer l'ancien handle de la ressource avant de retourner à l'application cliente.  L'exemple TESTDLL2 utilise cette méthode pour charger explicitement un menu.  
  
 Le fait de parcourir la liste a pour inconvénient de ralentir les opérations et d'exiger la gestion de plages d'ID de ressources.  L'avantage c'est qu'une application cliente qui lie à plusieurs DLL d'extension peut utiliser les ressources fournies par la DLL sans devoir spécifier le handle d'instance de DLL.  `AfxFindResourceHandle` est une API utilisée pour accompagner la liste des ressources pour rechercher une correspondance donnée.  Elle prend le nom et le type d'une ressource et retourne le handle de la ressource où elle a été trouvée en premier lieu \(ou la valeur NULL\).  
  
##  <a name="_mfcnotes_writing_an_application_that_uses_the_dll_version"></a> Dans une application qui utilise la version DLL  
  
### Les nécessités de l'application  
 Une application qui utilise la version partagée de MFC doit respecter certaines règles :  
  
-   Elle doit être un objet de `CWinApp` et suivre les règles standard pour la pompe des messages.  
  
-   Elle doit être compilée avec un ensemble de balises requises du compilateur \(voir ci\-dessous\).  
  
-   Elle doit se lier avec les bibliothèques d'importation de MFCxx.  En définissant des indicateurs requises du compilateur, les en\-têtes de MFC déterminent le temps de lien laquelle la bibliothèque l'application doit se lier.  
  
-   Pour exécuter le fichier exécutable, MFCxx.DLL doit être dans le chemin d'accès ou du répertoire système Windows.  
  
### Générer à l'aide de l'environnement de développement  
 Si vous utilisez le makefile interne avec la plupart des valeurs par défaut standard, vous pouvez modifier facilement le projet pour générer la version de DLL.  
  
 L'étape suivante suppose que vous possédez une application de MFC fonctionnante correctement liée à NAFXCWD.LIB \(débogage\) et NAFXCW.LIB \(pour la vente au détail\) et que vous voulez la convertir de façon à utiliser la version partagée de la bibliothèque MFC.  Vous exécutez l'environnement Visual C\+\+ et disposez d'un fichier projet interne.  
  
1.  Dans le menu **Projets**, cliquez sur **Propriétés**.  Dans la page de **Général** sous **Paramètres par défaut du projet**, définissez Microsoft Foundation Classes à **Utiliser les MFC dans une DLL partagée** \(MFCxx \(d\).dll\).  
  
### Génération avec NMAKE  
 Si vous utilisez la fonction externe de makefile Visual C\+\+, ou utilisez NMAKE directement, vous devez modifier votre makefile pour prendre en charge le compilateur et les options de l'éditeur de liens  
  
 Indicateurs requises du compilateur :  
  
 **\/D\_AFXDLL \/MD**  
 **\/D\_AFXDLL**  
  
 Les en\-têtes de MFC standard nécessitent que ce symbole soit défini :  
  
 **\/MD**  
 L'application doit utiliser la version DLL de la bibliothèque Runtime C  
  
 Toutes les autres indicateurs de compilateur suivent les valeurs par défaut de MFC \(par exemple, \_DEBUG pour le débogage\).  
  
 Modifiez la liste de l'éditeur de liens de bibliothèques.  Changez NAFXCWD.LIB en MFCxxD.LIB et changez NAFXCW.LIB en MFCxx.LIB.  Remplacez LIBC.LIB par MSVCRT.LIB.  Comme pour toute autre bibliothèque MFC il est important que MFCxxD.LIB soit placé **avant** toutes les bibliothèques C de temps d'exécution  
  
 Vous pouvez ajouter **\/D\_AFXDLL** à la vente au détail et déboguer les options du compilateur de ressources \(celle qui compilation en réalité des ressources à **\/r**\).  Cela donnerend votre executable final plus petit en partageant les ressources qui sont présentes dans les DLL MFC.  
  
 Une reconstruction complète est requise après ces modifications sont apportées.  
  
### Génération des exemples  
 La plupart des exemples de MFC peuvent être créées Visual C\+\+ ou d'un MAKEFILE partagé compatible avec NMAKE à partir de la ligne de commande.  
  
 Pour convertir l'un de ces exemples à utiliser MFCxx.DLL, vous pouvez charger le fichier .MAK dans Visual C\+\+ et définir les options de projet comme décrit ci\-dessus.  Si vous utilisez la version de NMAKE, vous pouvez spécifier « AFXDLL\=1 » sur la ligne de commande NMAKE, ce qui génèrera l'exemple à l'aide de bibliothèques MFC partagées.  
  
 L'exemple [DLLHUSK](../top/visual-cpp-samples.md) de concepts avancés par MFC est généré avec la version de DLL de MFC.  Cet exemple montre non seulement comment créer une application liée à MFCxx.DLL, mais il montre également d'autres fonctionnalités de l'option d'empaquetage DLL MFC telles que les DLL d'extension de MFC décrites plus loin dans cette note technique.  
  
### Empaqueter des notes  
 La version commerciale des DLL \(MFCxx\[U\].DLL\) est librement redistribuable.  La version de débogage des DLL n'est pas redistribuable librement et doit être utilisé uniquement lors de le développement de votre application.  
  
 Les DLL de débogage sont fournies d'informations de débogage.  À l'aide du débogueur Visual C\+\+, vous pouvez suivre l'exécution de l'application ainsi que de la DLL.  Les DLL de version \(MFCxx\[U\].DLL\) ne contiennent pas les informations de débogage.  
  
 Si vous personnalisez ou reconstruisez les DLL, vous devez les appeler quelque chose d'autre que « MFCxx » le fichier MFCDLL.MAK de MFC SRC décrit les options de génération et contient la logique pour renommer la DLL.  Renommer les fichiers est nécessaire, car ces DLL sont pas partagés entre de nombreuses applications de MFC.  Faire en sorte que votre version spéciale des DLL de MFC remplace celles installés sur le système peut désactiver une application de MFC utilisant les DLL MFC partagés.  
  
 Reconstruire les DLL MFC n'est pas recommandée.  
  
##  <a name="_mfcnotes_how_the_mfc30.dll_is_implemented"></a> Comment le MFCxx.DLL est implémenté  
 La section suivante décrit comment la DLL MFC \(MFCxx.DLL et MFCxxD.DLL\) est implémentée.  Comprendre les détails ici n'est également pas important si tout ce que vous voulez est utiliser les DLL de MFC pour votre application.  Les détails ici ne sont pas essentiels pour comprendre comment écrire une DLL d'extension de MFC, mais la description de cette implémentation peut vous aider à écrire votre propre DLL.  
  
### Vue d'ensemble de l'implémentation  
 La DLL MFC est réellement un cas spécial d'une DLL d'extension de MFC comme décrit ci\-dessus.  Elle possède un très grand nombre d'opérations pour un grand nombre de classes.  Il y a certaines opérations supplémentaires que nous faisons dans la DLL MFC qui la rendent encore plus spéciale qu'une DLL d'extension régulière  
  
### Win32 accomplit l'essentiel du travail à votre place.  
 La version 16 bits de MFC nécessitait plusieurs techniques spéciales, notamment les données de chaque application sur le segment de pile, la mise en place de segments spéciaux créés par le code d'assembly 80x86, les contextes d'exception pour chaque processus, et d'autres techniques.  Win32 prend directement en charge les données de chaque processus dans une DLL, qui est ce que vous désirez le plus souvent.  MFCxx.DLL est approximativement NAFXCW.LIB inséré dans une DLL.  Si vous cherchez source de MFC, vous trouverez très peu de \#ifdef \_AFXDLL, car il y a très peu de cas individuels qui doivent être traités.  Les cas individuels qui sont là le sont spécifiquement pour faire le traitement Win32 sur Windows 3.1 \(sinon appelé Win32s\).  Win32s ne prend pas en charge les données de la DLL pour chaque processus directement donc la DLL MFC doit utiliser des API Win32 de \(TLS\) de stockage local de threads pour obtenir des données locales du processus.  
  
### Impact sur les sources de bibliothèque, les fichiers supplémentaires  
 L'impact de **\_AFXDLL** sur les sources et les en\-têtes standard de bibliothèque de classes de MFC est relativement secondaire.  Il s'agit d'un fichier de version spéciale \(AFXV\_DLL.H\) ainsi qu'un fichier d'en\-tête supplémentaire \(AFXDLL\_.H\) inclus dans l'en\-tête principal d'AFXWIN.H.  L'en\-tête d'AFXDLL\_.H inclut la classe de **CDynLinkLibrary** et d'autres détails d'implémentation d'applications de **\_AFXDLL** ainsi que des DLL d'extension de MFC.  L'en\-tête d'AFXDLLX.H est fourni pour générer des DLL d'extension de MFC \(voir ci\-dessus pour plus d'informations\).  
  
 Les sources régulières de la bibliothèque MFC de MFC SRC ont un code conditionnel supplémentaire dans le \#ifdef de **\_AFXDLL**.  Un fichier source supplémentaire \(DLLINIT.CPP\) contient le code d'initialisation de DLL supplémentaire et d'autres colle pour la version partagée de MFC.  
  
 Pour générer la version partagée de MFC, des fichiers supplémentaires sont fournies. \(Voir plus bas pour des détails sur comment générer la DLL.\)  
  
-   Deux fichiers de .DEF sont utilisés pour exporter les points d'entrée de DLL MFC pour les versions de débogage \(MFCxxD.DEF\) et de lancement \(MFCxx.DEF\) de la DLL.  
  
-   Un fichier de .RC \(MFCDLL.RC\) contient toutes les ressources standard de MFC et une ressource VERSIONINFO de la DLL.  
  
-   Un fichier de .CLW \(MFCDLL.CLW\) est fourni pour permettre de parcourir les classes de MFC via ClassWizard.  Remarque : cette fonctionnalité n'est pas spécifique à la version DLL de MFC.  
  
### Gestion de la mémoire  
 Une application qui utilise MFCxx.DLL utilise un allocateur de mémoire courante fourni par MSVCRTxx.DLL, la DLL partagée de C\-runtime.  L'application, toutes les DLL d'extension, ainsi que les DLL MFC elles\-mêmes utilisent cet allocateur de mémoire partagée.  En utilisant une DLL partagée pour l'allocation de mémoire, les DLL MFC peuvent allouer de la mémoire qui se libèrera ultérieurement par l'application et inversement.  Étant donné que l'application et la DLL doivent utiliser le même allocateur, vous ne devez pas remplacer `operator new` global en C\+\+ ou `operator delete`.  Les mêmes règles s'appliquent au reste des routines d'allocation de mémoire runtime C \(telles que `malloc`, `realloc`, **libérer**, entre autres\).  
  
### Ordinaux et classe \_\_declspec\(dllexport\) et nommage de DLL  
 Nous utilisons ne pas la fonctionnalité de `class`**\_\_declspec\(dllexport\)** du compilateur C\+\+.  À la place, la liste d'exportation est incluse avec les sources de la bibliothèque de classes \(MFCxx.DEF et MFCxxD.DEF\).  Seuls ces quelques jeux de points d'entrée \(les fonctions et les données\) sont exportés.  D'autres symboles, tels que les fonctions privées ou les classes d'implémentation de MFC, ne sont pas exportés. Toutes les opérations sont effectuées par ordinal sans nom de chaîne dans la table de noms résidentes ou non\-résidente.  
  
 Utiliser `class` **\_\_declspec\(dllexport\)** peut être une alternative valable pour générer plusieurs petits DLL, mais dans le cas d'un grand DLL comme MFC, le mécanisme de l'exportation par défaut a des limites d'efficacité et de capacité.  
  
 Ce que tout cela veut dire est que nous pouvons empaqueter un grand nombre de fonctionnalités dans la version MFCxx.DLL qui ne pèse environ que 800 Ko sans compromettre beaucoup le temps exécution ou la vitesse de chargement.  MFCxx.DLL aurait été plus grand de 100K si cette technique n'a pas été utilisée.  Cela permet également d'ajouter des points d'entrée supplémentaires à la fin du fichier .DEF pour permettre un contrôle de version simple sans compromettre l'efficacité en taille et en vitesse lors de l'exportation par ordinal.  Les grands changements de version dans la bibliothèque de classes de MFC modifie le nom de la bibliothèque.  Autrement dit, MFC30.DLL est la DLL redistribuable contenant la version 3,0 de la bibliothèque de classes de MFC.  Une mise à niveau de cette DLL, par exemple dans un hypothétique MFC 3.1, la DLL serait nommée MFC31.DLL à la place.  Là encore, si vous modifiez le code source de MFC pour produire une version spéciale de la DLL MFC, utilisez un nom différent \(et de préférence sans « MFC » dans le nom\).  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)