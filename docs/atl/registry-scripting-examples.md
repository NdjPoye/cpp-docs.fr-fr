---
title: "Registry Scripting Examples | Microsoft Docs"
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
  - "registrar scripts [ATL]"
  - "Registre, Registrar"
  - "scripts, exemples"
  - "scripts, Registrar scripts"
ms.assetid: b6df80e1-e08b-40ee-9243-9b381b172460
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Registry Scripting Examples
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les exemples de script dans cette rubrique montrent comment ajouter une clé à la base de registres, stocker le serveur COM d'inscription, et spécifier plusieurs analysez les arborescences.  
  
## Ajoutez une clé à HKEY\_CURRENT\_USER  
 Ce qui suit analyse l'arborescence illustre un script simple qui ajoute une clé unique à la base de registres.  En particulier, le script ajoute la clé, `MyVeryOwnKey`, à `HKEY_CURRENT_USER`.  Il assigne également la valeur de chaîne par défaut d' `HowGoesIt?` à la nouvelle clé :  
  
```  
HKEY_CURRENT_USER  
{  
   'MyVeryOwnKey' = s 'HowGoesIt?'  
}  
```  
  
 Ce script peut être facilement étendu pour définir plusieurs sous\-clés comme suit :  
  
```  
HKCU  
{  
   'MyVeryOwnKey' = s 'HowGoesIt?'  
   {  
      'HasASubkey'  
      {  
         'PrettyCool?' = d '55'  
         val 'ANameValue' = s 'WithANamedValue'  
      }  
   }  
}  
```  
  
 Maintenant, le script ajoute une sous\-clé, `HasASubkey`, à `MyVeryOwnKey`.  À cette valeur, il ajoute la sous\-clé d' `PrettyCool?` \(avec une valeur par défaut d' `DWORD` de 55\) et l' `ANameValue` nommé valeur \(avec une valeur de chaîne d' `WithANamedValue`\).  
  
##  <a name="_atl_register_the_registrar_com_server"></a> Inscrivez le serveur COM d'inscription  
 Le script suivant enregistre le serveur COM d'inscription lui\-même.  
  
```  
HKCR  
{  
   ATL.Registrar = s 'ATL Registrar Class'  
   {  
      CLSID = s '{44EC053A-400F-11D0-9DCD-00A0C90391D3}'  
   }  
   NoRemove CLSID  
   {  
      ForceRemove {44EC053A-400F-11D0-9DCD-00A0C90391D3} =  
                   s 'ATL Registrar Class'  
      {  
         ProgID = s 'ATL.Registrar'  
         InprocServer32 = s '%MODULE%'  
         {  
            val ThreadingModel = s 'Apartment'  
         }  
      }  
   }  
}  
```  
  
 Au moment de l'exécution, ce analysez l'arborescence ajoute la clé d' `ATL.Registrar` à `HKEY_CLASSES_ROOT`.  À cette clé, il puis :  
  
-   Spécifie `ATL Registrar Class` comme valeur de chaîne par défaut de la clé.  
  
-   Ajoute `CLSID` comme valeur.  
  
-   Spécifie `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` pour `CLSID`.  \(Cette valeur est le CLSID du registre pour une utilisation avec `CoCreateInstance`.\)  
  
 Étant donné qu' `CLSID` est partagé, il ne doit pas être supprimé dans annulent l'enregistrement mode.  L'instruction, `NoRemove CLSID`, le fait en indiquant cet `CLSID` doit être ouvert en mode de registre et ignoré dans désinscrivez l'état.  
  
 L'instruction d' `ForceRemove` fournit une fonction de gestion interne en supprimant une clé et toutes ses sous\-clés avant de recréer la clé.  Cela peut être utile si les noms des sous\-clés ont changé.  Dans cet exemple de script, `ForceRemove` vérifie si `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` existe déjà.  Si tel est le cas, `ForceRemove`:  
  
-   Supprime de manière récursive `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` et toutes ses sous\-clés.  
  
-   Recrée `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`.  
  
-   Ajoute `ATL Registrar Class` comme valeur de chaîne par défaut pour `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`.  
  
 L'arborescence d'analyser maintenant ajoute deux nouvelles sous\-clés à `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`.  La première clé, `ProgID`, obtient une valeur de chaîne par défaut qui est l'identificateur programmatique.  La deuxième clé, `InprocServer32`, obtient une valeur de chaîne par défaut, `%MODULE%`, qui est une valeur de préprocesseur expliquée dans la section, [Utilisation de paramètres remplaçables \(le préprocesseur du registre\)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md), de cet article.  `InprocServer32` obtient également une valeur nommée, `ThreadingModel`, avec une valeur de chaîne d' `Apartment`.  
  
## Spécifiez plusieurs analysent les arborescences  
 Pour spécifier plusieurs analysez l'arborescence dans un script, affectez simplement une arborescence à la fin d'une autre.  Par exemple, le script suivant ajoute la clé, `MyVeryOwnKey`, en arborescences d'analyser pour `HKEY_CLASSES_ROOT` et `HKEY_CURRENT_USER`:  
  
```  
HKCR  
{  
   'MyVeryOwnKey' = s 'HowGoesIt?'  
}  
HKEY_CURRENT_USER  
{  
   'MyVeryOwnKey' = s 'HowGoesIt?'  
}  
```  
  
> [!NOTE]
>  Dans un script d'inscription, 4K est la taille maximale de jeton.  \(Le jeton d'Un est un élément reconnaissable dans la syntaxe.\) Dans l'exemple précédent de script, `HKCR`, `HKEY_CURRENT_USER`, `'MyVeryOwnKey'`, et `'HowGoesIt?'` sont les jetons.  
  
## Voir aussi  
 [Creating Registrar Scripts](../atl/creating-registrar-scripts.md)