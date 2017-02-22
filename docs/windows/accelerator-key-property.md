---
title: "Key, propri&#233;t&#233; d&#39;un acc&#233;l&#233;rateur | Microsoft Docs"
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
  - "Key (propriété)"
ms.assetid: d1570cd9-b414-4cd6-96bd-47c38281eaca
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Key, propri&#233;t&#233; d&#39;un acc&#233;l&#233;rateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous trouverez ci\-dessous les entrées valides pour la propriété Key dans la table d'accélérateurs :  
  
-   Un entier compris entre 0 et 255 au format décimal.  Cette valeur détermine si la valeur est traitée comme une valeur ASCII ou ANSI de la façon suivante :  
  
    -   Les nombres à un chiffre sont toujours interprétés comme la touche correspondante, plutôt que comme des valeurs ASCII ou ANSI.  
  
    -   Les valeurs comprises entre 1 et 26, lorsqu'elles sont précédées de zéros, sont interprétées comme ^A à ^Z, ce qui représente la valeur ASCII des lettres de l'alphabet lorsque la touche CTRL est enfoncée.  
  
    -   Les valeurs comprises entre 27\-32 sont toujours interprétées comme des valeurs décimales à trois chiffres comprises entre 027 et 032.  
  
    -   Les valeurs 033 à 255, qu'elles soient ou non précédées par des zéros sont interprétées comme des valeurs ANSI.  
  
-   Un caractère du clavier unique.  Les majuscules A – Z ou les chiffres 0 – 9 peuvent être des valeurs de touche virtuelles ou ASCII ; les autres caractères sont uniquement ASCII.  
  
-   Un caractère du clavier unique situé dans la plage A – Z \(majuscule uniquement\), précédé par un signe insertion ^ \(par exemple, ^C\).  Cela entre la valeur ASCII de la touche lorsque la touche CTRL est enfoncée.  
  
    > [!NOTE]
    >  Lorsque vous entrez une valeur ASCII, les options de la propriété Modifier sont limitées.  La seule touche de contrôle disponible est la touche ALT.  
  
-   N'importe quel identificateur valide de touche virtuelle.  La zone de liste déroulante de la touche dans la table d'accélérateurs contient une liste des identificateurs de touche virtuelle standard.  
  
    > [!TIP]
    >  Une autre méthode pour définir une touche accélérateur est de cliquer avec le bouton droit sur une entrée ou plusieurs entrées dans la table d'accélérateurs, de choisir **Touche enfoncée suivante** dans le menu contextuel et d'appuyer sur les touches ou les combinaisons de touches au clavier.  La commande **Touche enfoncée suivante** est également disponible dans le menu **Edition**.  
  
## Configuration requise  
 Win32  
  
## Voir aussi  
 [Setting Accelerator Properties](../windows/setting-accelerator-properties.md)   
 [Editing in an Accelerator Table](../windows/editing-in-an-accelerator-table.md)   
 [Accelerator Editor](../mfc/accelerator-editor.md)