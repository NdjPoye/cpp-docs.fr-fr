---
title: "D&#233;limiteurs pour les balises de documentation Visual&#160;C++ | Microsoft Docs"
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
  - "documentation XML, délimiteurs"
ms.assetid: debfbdd9-63fa-4c58-a18e-a4d203d241d7
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# D&#233;limiteurs pour les balises de documentation Visual&#160;C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'utilisation des balises de documentation requiert les séparateurs, qui indique au compilateur où un commentaire de documentation commence et se termine.  
  
 Vous pouvez utiliser les types de délimiteurs ci\-dessous avec les balises de documentation XML :  
  
 `///`  
 C'est le formulaire qui est indiqué dans les exemples de documentation et utilisée par les modèles de projet Visual C\+\+.  
  
 `/** */`  
 Ce sont les séparateurs multilignes.  
  
 Il existe des règles de mise en forme en utilisant les séparateurs d' `/** */` :  
  
-   Pour la ligne qui contient le séparateur d' `/**`, si le reste de la ligne est l'espace blanc, la ligne n'est pas traitée pour les commentaires.  Si le premier caractère est un espace blanc, ce caractère d'espace blanc est ignoré et le reste de la ligne est traité.  Sinon, tout le texte de la ligne qui suit le délimiteur `/**` est traité comme une partie du commentaire.  
  
-   Pour la ligne qui contient le séparateur d' `*/`, s'il n'existe qu'un espace blanc jusqu'au séparateur d' `*/`, que la ligne est ignoré.  Sinon, le texte précédant le délimiteur `*/` sur la ligne est traité comme une partie du commentaire, sujet aux règles des critères spéciaux décrites dans le paragraphe suivant.  
  
-   Pour ligne après celui qui commence par le séparateur d' `/**`, le compilateur recherche un modèle commun au début de chaque ligne qui se compose de l'espace blanc facultatif et d'un astérisque \(`*`\), suivie de l'espace blanc plus facultatif.  Si le compilateur recherche un ensemble commun de caractères au début de chaque ligne, il ignore ce modèle pour toutes les lignes après le séparateur d' `/**`, jusqu'à et éventuellement y compris la ligne qui contient le séparateur d' `*/` .  
  
 Voici quelques exemples :  
  
-   La seule partie du commentaire suivant qui sera traitée est la ligne commençant par `<summary>`.  Les deux formats suivants de balise produisent les mêmes commentaires :  
  
    ```  
    /**  
    <summary>text</summary>   
    */  
    /** <summary>text</summary> */  
    ```  
  
-   Le compilateur applique un modèle de « \* » pour ignorer au début de la deuxième et troisième lignes.  
  
    ```  
    /**  
     * <summary>  
     *  text </summary>*/  
    ```  
  
-   Le compilateur ne trouve pas de modèle dans ce commentaire car il n'existe aucun astérisque sur la deuxième ligne.  Par conséquent, tout le texte sur les deuxième et troisième lignes, en haut de jusqu'à `*/`, sera traité dans le cadre de le commentaire.  
  
    ```  
    /**  
     * <summary>  
       text </summary>*/  
    ```  
  
-   Le compilateur ne trouve pas de modèle dans ce commentaire pour deux raisons.  D'abord, il n'y a aucune ligne qui commence par un nombre cohérent des espaces avant l'astérisque.  D'autre part, la cinquième ligne commence par une tabulation, qui ne correspond pas à des espaces.  Par conséquent, tout le texte de la deuxième ligne jusqu'à `*/` sera traité dans le cadre de le commentaire.  
  
    ```  
    /**  
      * <summary>  
      * text   
     *  text2  
       *  </summary>  
    */  
    ```  
  
## Voir aussi  
 [Documentation XML](../ide/xml-documentation-visual-cpp.md)