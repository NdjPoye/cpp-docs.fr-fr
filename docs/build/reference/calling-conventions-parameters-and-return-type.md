---
title: "Conventions d&#39;appel, param&#232;tres et type de retour | Microsoft Docs"
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
  - "conventions d'appel, fonctions d'assistance"
  - "fonctions d'assistance, conventions d'appel"
  - "fonctions d'assistance, types de retour"
ms.assetid: 0ffa4558-6005-4803-be95-7a8ec8837660
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Conventions d&#39;appel, param&#232;tres et type de retour
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le prototype d'une routine d'assistance est :  
  
```  
FARPROC WINAPI __delayLoadHelper2(   
   PCImgDelayDescr pidd,  
   FARPROC * ppfnIATEntry  
);  
```  
  
 où :  
  
 `pidd`  
 Pointeur `const` vers un `ImgDelayDescr` \(voir delayimp.h\) qui contient les décalages de diverses données liées aux importations, un horodatage pour les informations de liaison, ainsi qu'un ensemble d'attributs qui fournissent des informations supplémentaires sur le contenu du descripteur.  Actuellement, il n'existe qu'un seul attribut, `dlattrRva`, ce qui indique que les adresses dans le descripteur sont des adresses virtuelles relatives \(par opposition à des adresses virtuelles\).  
  
 Pour obtenir la définition de la structure `PCImgDelayDescr`, voir [Définitions des structures et constantes](../../build/reference/structure-and-constant-definitions.md).  
  
 `ppfnIATEntry`  
 Pointeur vers l'emplacement dans la table IAT \(Import Address Table\) de chargement différé qui doit être mis à jour avec l'adresse de la fonction importée.  La routine d'assistance doit stocker la même valeur qu'elle retournera dans cet emplacement.  
  
## Valeurs de retour attendues  
 Si la fonction réussit, elle retourne l'adresse de la fonction importée.  
  
 Si la fonction échoue, elle lève une exception et retourne 0.  Trois types d'exceptions peuvent être levées :  
  
-   paramètre non valide, ce qui se produit si les attributs dans `pidd` ne sont pas spécifiés correctement ;  
  
-   `LoadLibrary` a échoué sur la DLL spécifiée ;  
  
-   échec de `GetProcAddress`.  
  
 La gestion de ces exceptions est de votre responsabilité.  
  
## Notes  
 La convention d'appel pour la fonction d'assistance est `__stdcall`.  Le type de la valeur de retour n'est pas pertinent, si bien que FARPROC est utilisé.  Cette fonction dispose d'une liaison C.  
  
 La valeur de retour de l'assistant de chargement différé doit être stockée dans l'emplacement du pointeur de fonction fourni, à moins que vous vouliez que votre routine d'assistance soit utilisée en tant que hook de notification.  Dans ce cas, votre code a la responsabilité de trouver le pointeur de fonction approprié à retourner.  Le code thunk que l'éditeur de liens génère prend ensuite cette valeur de retour comme cible réelle de l'importation et y accède directement.  
  
## Exemple  
 Le code suivant illustre l'implémentation d'une fonction hook simple.  
  
```  
FARPROC WINAPI delayHook(unsigned dliNotify, PDelayLoadInfo pdli)  
{  
    switch (dliNotify) {  
        case dliStartProcessing :  
  
            // If you want to return control to the helper, return 0.  
            // Otherwise, return a pointer to a FARPROC helper function  
            // that will be used instead, thereby bypassing the rest   
            // of the helper.  
  
            break;  
  
        case dliNotePreLoadLibrary :  
  
            // If you want to return control to the helper, return 0.  
            // Otherwise, return your own HMODULE to be used by the   
            // helper instead of having it call LoadLibrary itself.  
  
            break;  
  
        case dliNotePreGetProcAddress :  
  
            // If you want to return control to the helper, return 0.  
            // If you choose you may supply your own FARPROC function   
            // address and bypass the helper's call to GetProcAddress.  
  
            break;  
  
        case dliFailLoadLib :   
  
            // LoadLibrary failed.  
            // If you don't want to handle this failure yourself, return 0.  
            // In this case the helper will raise an exception   
            // (ERROR_MOD_NOT_FOUND) and exit.  
            // If you want to handle the failure by loading an alternate   
            // DLL (for example), then return the HMODULE for   
            // the alternate DLL. The helper will continue execution with   
            // this alternate DLL and attempt to find the  
            // requested entrypoint via GetProcAddress.  
  
            break;  
  
        case dliFailGetProc :  
  
            // GetProcAddress failed.  
            // If you don't want to handle this failure yourself, return 0.  
            // In this case the helper will raise an exception   
            // (ERROR_PROC_NOT_FOUND) and exit.  
            // If you choose you may handle the failure by returning   
            // an alternate FARPROC function address.  
  
            break;  
  
        case dliNoteEndProcessing :   
  
            // This notification is called after all processing is done.   
            // There is no opportunity for modifying the helper's behavior  
            // at this point except by longjmp()/throw()/RaiseException.   
            // No return value is processed.  
  
            break;  
  
        default :  
  
            return NULL;  
    }  
  
    return NULL;  
}  
  
/*   
and then at global scope somewhere  
PfnDliHook __pfnDliNotifyHook2 = delayHook;  
*/  
```  
  
## Voir aussi  
 [Présentation de la fonction d'assistance](../../build/reference/understanding-the-helper-function.md)