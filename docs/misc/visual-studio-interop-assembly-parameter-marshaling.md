---
title: "Marshaling des param&#232;tres d’assembly PIA Visual Studio | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "dépannage des assemblys PIA (Primary Interop Assembly) du Kit SDK Visual Studio"
  - "assemblys PIA, marshaling des paramètres"
  - "assemblys PIA, dépannage"
ms.assetid: 89123eae-0fef-46d5-bd36-3d2a166b14e3
caps.latest.revision: 24
caps.handback.revision: 24
manager: "douge"
---
# Marshaling des param&#232;tres d’assembly PIA Visual Studio
VSPackages écrits en code managé peut devoir appeler ou être appelé par du code non managé COM.  En général, les arguments de méthode sont transformés, ou marshalés, automatiquement par le marshaleur d'interopérabilité.  Toutefois, il peut arriver que des arguments ne peuvent pas être transformés de façon simple.  Dans ces cas, les paramètres d'interopérabilité du prototype de méthode d'assembly sont utilisés pour correspondre aux paramètres de fonction COM mieux possible.  Pour plus d'informations, consultez [Interop Marshaling](../Topic/Interop%20Marshaling.md).  
  
## suggestions générales  
  
##### lisez la documentation de référence  
 Un moyen efficace de détecter les problèmes d'interopérabilité consiste à lire la documentation de référence pour chaque méthode.  
  
 La documentation de référence pour chaque méthode contient trois sections pertinentes :  
  
-   Le prototype de fonction de [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] COM.  
  
-   le prototype d'interopérabilité de méthode d'assembly.  
  
-   La liste des paramètres COM et d'une brève description de chaque.  
  
##### recherchez les différences entre les deux prototypes  
 La plupart des problèmes d'interopérabilité dérivent les incompatibilités entre la définition d'un particulier dans une interface COM et la définition du même type dans les assemblys d'interopérabilité de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] .  Par exemple, considérez la différence dans la possibilité de passer une valeur d' `null` dans \[out\] un paramètre.  Vous devez rechercher les différences entre les deux prototypes et considérer leurs ramifications les données qui sont passées.  
  
##### lisez les définitions de paramètre  
 lisez les définitions de paramètre.  COM est moins strict que le common langage runtime \(CLR\) à propos de combiner des types de données dans un seul paramètre.  Les interfaces COM de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] pleinement parti de cette flexibilité.  Tout paramètre qui peut passer ou requiert une valeur non standard ou type de données, tel qu'une valeur de constante dans un paramètre de pointeur, doit être décrit comme tels dans la documentation.  
  
### Objets d'IUnknown passés comme de type void \*\*  
 Recherchez \[out\] les paramètres définis comme type `void **` dans l'interface COM, mais qui sont définis comme `[``iid_is``]` dans le prototype d'interopérabilité de méthode d'assembly de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] .  
  
 Parfois, une interface COM génère un objet d' `IUnknown` , et l'interface COM puis les passe en tant que type `void **`.  Ces interfaces sont particulièrement importantes parce que si la variable est définie par \[out\] dans le fichier IDL, l'objet d' `IUnknown` référence\-est compté avec la méthode d' `AddRef` .  Une fuite de mémoire se produit si l'objet n'est pas gérées correctement.  
  
> [!NOTE]
>  Un objet d' `IUnknown` créé par l'interface COM et retourner dans \[out\] une variable entraîne une fuite de mémoire s'il n'est pas explicitement désactivé.  
  
 Les méthodes managées qui gèrent de ces objets doivent concerner <xref:System.IntPtr> comme pointeur vers un objet d' `IUnknown` , et appelez la méthode d' <xref:System.Runtime.InteropServices.Marshal.GetObjectForIUnknown%2A> pour obtenir l'objet.  L'appelant doit ensuite caster la valeur de retour à n'importe quel type est approprié.  Lorsque l'objet n'est plus nécessaire, appelez <xref:System.Runtime.InteropServices.Marshal.Release%2A> pour le libérer.  
  
 Voici un exemple d'appeler la méthode d' <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.QueryViewInterface%2A> et de gérer l'objet d' `IUnknown` correctement :  
  
```  
MyClass myclass;  
Object object;  
IntPtr pObj;  
Guid iid = Typeof(MyClass).Guid;  
int hr = windowFrame.QueryViewInterface(ref iid, out pObj);     
if (NativeMethods.Succeeded(hr))   
{  
    try   
    {  
        object = Marshal.GetObjectForIUnknown(pObj);  
        myclass = object;  
    }  
    finally   
    {  
        Marshal.Release(pObj);  
    }  
}  
else   
{  
    // error calling QueryViewInterface  
}  
```  
  
> [!NOTE]
>  Les méthodes suivantes sont connues pour passer des pointeurs d'objet d' `IUnknown` comme type <xref:System.IntPtr>.  Gérez\-les comme décrit dans cette section.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CreateProject%2A>  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsOwnedProjectFactory.InitializeForOwner%2A>  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetNestedHierarchy%2A>  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.CreateProject%2A>  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.QueryViewInterface%2A>  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg2.get_CfgType%2A>  
  
### paramètres \[out\] facultatifs  
 Recherchez les paramètres définis comme \[out\] type de données \(`int`, `object`, etc.\) dans l'interface COM, mais qui sont définis en tant que tableau du même type de données dans le prototype d'interopérabilité de méthode d'assembly de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] .  
  
 Certaines interfaces COM, telles que l' <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2.GetCfgs%2A>, traitent \[out\] les paramètres comme facultatifs.  Si un objet n'est pas requis, ces interfaces COM retournent un pointeur d' `null` comme valeur du paramètre au lieu de \[out\] créer l'objet.  Ce problème est dû au design.  Pour ces interfaces, les pointeurs d' `null` sont assumés dans le cadre de le comportement correct du VSPackage, et aucune erreur n'est retournée.  
  
 Étant donné que le CLR ne permet pas à \[out\] la valeur d'un paramètre en `null`, une partie du comportement conçu de ces interfaces n'est pas directement disponible dans le code managé.  Les méthodes d'interopérabilité d'assembly de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] pour les interfaces affectées fonctionnent autour de le problème en définissant les paramètres appropriés en tant que tableaux parce que le CLR permet le passage de tableaux d' `null` .  
  
 Les implémentations managées de ces méthodes doivent mettre un tableau d' `null` dans le paramètre lorsqu'il n'y a aucun élément à être retourné.  Sinon, créez un tableau d'un élément du type correct et placez la valeur de retour dans le tableau.  
  
 Les méthodes managées qui acceptent les informations des interfaces avec les paramètres facultatifs \[out\] acceptent le paramètre en tant que tableau.  Examinez uniquement la valeur du premier élément du tableau.  Si ce n'est pas `null`, traitez le premier élément comme s'il s'agissait du paramètre d'origine.  
  
### Passer des constantes dans les paramètres de pointeur  
 Recherchez les paramètres définis comme \[in\] pointeurs dans l'interface COM, mais qui sont définis comme <xref:System.IntPtr> dans le prototype d'interopérabilité de méthode d'assembly de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] .  
  
 Un problème similaire se produit lorsqu'une interface COM passe une valeur spéciale, telle que 0, \-1, ou \- 2, au lieu d'un pointeur d'objet.  Contrairement à [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)], le CLR ne permet pas aux constantes pour être casté en tant qu'objets.  au lieu de cela, l'assembly d'interopérabilité de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] définit le paramètre comme type d' <xref:System.IntPtr> .  
  
 Les implémentations managées de ces méthodes doivent tirer parti du fait que la classe d' <xref:System.IntPtr> a `int` et des constructeurs d' `void *` pour créer <xref:System.IntPtr> d'un objet ou d'une constante entière, selon le cas.  
  
 Les méthodes managées qui acceptent des paramètres d' <xref:System.IntPtr> de ce type doivent utiliser les opérateurs de conversion de type d' <xref:System.IntPtr> pour gérer les résultats.  Tout d'abord convertir <xref:System.IntPtr> à `int` et testez \-le par rapport à les constantes entières appropriées.  Si valeur ne correspond, convertissez \-la en objet du type requis et continuez.  
  
 Pour obtenir des exemples de cela, consultez l' <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> et l' <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenSpecificEditor%2A>.  
  
### OLE valeurs de retour passées \[out\] en tant que paramètres  
 Recherchez les méthodes qui ont une valeur de retour d' `retval` dans l'interface COM, mais qui ont une valeur de retour d' `int` et un paramètre supplémentaire \[out\] de tableau dans le prototype d'interopérabilité de méthode d'assembly de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] .  Il doit être clair que ces méthodes requièrent une gestion spéciale car les prototypes d'interopérabilité de méthode d'assembly de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] ont un plus de paramètre que les méthodes d'interface COM.  
  
 Nombre d'interfaces COM qui traitent OLE activité envoyer des informations sur le OLE état revient au programme appelant enregistré dans la valeur de retour d' `retval` de l'interface.  Au lieu d'utiliser une valeur de retour, les méthodes d'interopérabilité correspondantes d'assembly de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] envoient des informations sur le programme appelant stocké dans \[out\] un paramètre de tableau.  
  
 Les implémentations managées de ces méthodes doivent créer un tableau à un seul élément du même type que \[out\] le paramètre et le placer dans le paramètre.  La valeur de l'élément de tableau doit être identique à COM approprié `retval`.  
  
 Les méthodes managées appellent des interfaces de ce type doivent extraire le premier élément hors \[out\] de le tableau.  Cet élément peut être traité comme une valeur de retour d' `retval` de l'interface COM correspondante.  
  
## Voir aussi  
 [Interop Marshaling](http://msdn.microsoft.com/fr-fr/a95fdb76-7c0d-409e-a77e-0349b1ea1490)   
 [Interop Marshaling](../Topic/Interop%20Marshaling.md)   
 [Troubleshooting Interoperability](../Topic/Troubleshooting%20Interoperability%20\(Visual%20Basic\).md)   
 [VSPackages gérés](../misc/managed-vspackages.md)