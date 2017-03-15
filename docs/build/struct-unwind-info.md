---
title: "struct UNWIND_INFO | Microsoft Docs"
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
ms.assetid: f0aee906-a1b9-44cc-a8ad-463637bd5411
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# struct UNWIND_INFO
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La structure des informations sur les données de déroulement est utilisée pour enregistrer les effets d'une fonction sur le pointeur de pile et l'emplacement auquel les registres non volatils sont enregistrés sur la pile :  
  
|||  
|-|-|  
|UBYTE: 3|Version|  
|UBYTE: 5|Flags|  
|UBYTE|Taille du prologue|  
|UBYTE|Nombre de codes de déroulement|  
|UBYTE: 4|Registre du frame|  
|UBYTE: 4|Offset du registre du frame \(mis à l'échelle\)|  
|USHORT \* n|Tableau de codes de déroulement|  
|variable|Peut se présenter sous la forme \(1\) ou \(2\) ci\-dessous|  
  
 \(1\) Gestionnaire d'exceptions  
  
|||  
|-|-|  
|ULONG|Adresse du gestionnaire d'exceptions|  
|variable|Données du gestionnaire spécifique au langage \(facultatif\)|  
  
 \(2\) Des informations liées de déroulement  
  
|||  
|-|-|  
|ULONG|Adresse de début de fonction|  
|ULONG|Adresse de fin de fonction|  
|ULONG|Adresse des informations de déroulement|  
  
 La structure UNWIND\_FUNCTION doit être alignée sur un DWORD en mémoire.  Vous trouverez ci\-dessous la signification de chaque champ :  
  
 **Version**  
 Numéro de version des données de déroulement \(actuellement 1\).  
  
 **Flags**  
 Trois indicateurs sont actuellement définis :  
  
 UNW\_FLAG\_EHANDLER la fonction a un gestionnaire d'exceptions qui doit être appelé en recherchant fonctionne ce besoin d'examiner des exceptions.  
  
 UNW\_FLAG\_UHANDLER la fonction a un gestionnaire de terminaisons qui doit être appelé via un déroulement une exception.  
  
 Cette structure d'informations de progression d'UNW\_FLAG\_CHAININFO n'est pas la principale pour la procédure.  Par contre, l'entrée des informations de déroulement chaînées est le contenu d'une entrée RUNTIME\_FUNCTION antérieure.  Consultez le texte suivant pour obtenir une explication des structures d'informations de déroulement chaînées.  Si cet indicateur est défini, les indicateurs UNW\_FLAG\_EHANDLER et UNW\_FLAG\_UHANDLER doivent être effacés.  Les champs du registre du frame et de l'allocation de pile fixe doivent posséder les mêmes valeurs que dans les informations de déroulement principales.  
  
 **Taille du prologue**  
 Longueur du prologue de fonction en octets.  
  
 **Nombre de codes de déroulement**  
 Nombre d'emplacements dans le tableau de codes de déroulement.  Notez que certains codes de déroulement \(par exemple, UWOP\_SAVE\_NONVOL\) exigent plusieurs emplacements dans le tableau.  
  
 **Registre du frame**  
 Si ce champ a une valeur différente de zéro, la fonction utilise un pointeur de frame, et ce champ correspond au numéro du registre non volatil utilisé comme pointeur de frame, à l'aide du même encodage que pour le champ d'information d'opération des nœuds UNWIND\_CODE.  
  
 **Offset du registre du frame \(mis à l'échelle\)**  
 Si le champ du registre du frame a une valeur différente de zéro, il s'agit de l'offset mis à l'échelle de RSP qui s'applique au registre FP lorsqu'il est défini.  Le régulateur FP réel a la valeur RSP \+ 16 \* ce nombre, ce qui permet des offsets de 0 à 240.  Cela permet de pointer le régulateur FP vers le milieu de l'allocation de pile locale pour les frames de pile dynamiques, ce qui offre une meilleure densité de code via des instructions plus courtes \(plus d'instructions peuvent utiliser la forme offset signé de 8 bits\).  
  
 **Tableau de codes de déroulement**  
 Tableau des éléments qui expliquent l'effet du prologue sur les registres non volatils et RSP.  Consultez la section relative à UNWIND\_CODE pour connaître la signification des différents éléments.  À des fins d'alignement, ce tableau possèdera toujours un nombre pair d'entrées, avec la dernière entrée éventuellement inutilisée \(auquel cas le tableau comptera une entrée de plus que spécifié par le champ du nombre de codes de déroulement\).  
  
 **Adresse du gestionnaire d'exceptions**  
 Pointeur relatif à l'image désignant le gestionnaire d'exceptions\/de terminaisons spécifique au langage de la fonction \(si l'indicateur UNW\_FLAG\_CHAININFO est effacé et si l'un des indicateurs UNW\_FLAG\_EHANDLER ou UNW\_FLAG\_UHANDLER est défini\).  
  
 **Données du gestionnaire spécifique au langage**  
 Données du gestionnaire d'exceptions spécifique au langage de la fonction.  Le format de ces données n'est pas défini et est complètement déterminé par le gestionnaire d'exceptions spécifique utilisé.  
  
 **Informations de déroulement chaînées**  
 Si indicateur UNW\_FLAG\_CHAININFO est défini, la structure UNWIND\_INFO se termine par trois UWORD.  Ces UWORD représentent les informations RUNTIME\_FUNCTION pour la fonction du déroulement chaîné.  
  
## Voir aussi  
 [Données de déroulement pour la gestion des exceptions et la prise en charge du débogueur](../build/unwind-data-for-exception-handling-debugger-support.md)