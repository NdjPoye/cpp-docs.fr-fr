---
title: "/SECTION (Sp&#233;cifier les attributs de section) | Microsoft Docs"
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
  - "/section"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/SECTION (option de l'éditeur de liens)"
  - "attributs de section"
  - "SECTION (option de l'éditeur de liens)"
  - "-SECTION (option de l'éditeur de liens)"
ms.assetid: 92b69d81-e421-462e-b46f-7d0dff9b9d16
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /SECTION (Sp&#233;cifier les attributs de section)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/SECTION:name,[[!]{DEKPRSW}][,ALIGN=#]  
```  
  
## Notes  
 L'option \/SECTION modifie les attributs d'une section, en substituant les attributs qui ont été définis lors de la compilation du fichier .obj associé à la section.  
  
 Une section est un fichier PE \(Portable Executable\) qui équivaut à peu près à un segment ou aux ressources d'un nouveau fichier exécutable \(New Executable\).  Les sections contiennent du code ou des données.  Contrairement aux segments, ce sont des blocs de mémoire contiguë sans contrainte de taille.  Certaines sections contiennent du code ou des données que votre programme a déclarés et qu'il utilise directement ; d'autres sections de données sont créées pour vous par l'éditeur de liens et le gestionnaire de bibliothèques \(lib.exe\) et contiennent des informations essentielles pour le système d'exploitation.  Pour plus d'informations sur les nouveaux fichiers exécutables, consultez l'article de la Base de connaissances Q65122, « Executable\-File Header Format » \(article en anglais\).  Vous trouverez les articles de la Base de connaissances dans la bibliothèque MSDN ou à l'adresse [http:\/\/search.support.microsoft.com](http://support.microsoft.com).  
  
 Spécifiez le signe deux\-points \(:\) et un *nom* de section.  Ce *nom* respecte la casse.  
  
 N'utilisez pas les noms suivants, car ils entrent en conflit avec les noms standard.  Par exemple, .sdata est utilisé sur les plateformes RISC :  
  
-   .arch  
  
-   .bss  
  
-   .data  
  
-   .edata  
  
-   .idata  
  
-   .pdata  
  
-   .rdata  
  
-   .reloc  
  
-   .rsrc  
  
-   .sbss  
  
-   .sdata  
  
-   .srdata  
  
-   .text  
  
-   .xdata  
  
 Spécifiez un ou plusieurs attributs pour la section.  Les caractères d'attribut, répertoriés ci\-après, ne respectent pas la casse.  Vous devez spécifier tous les attributs que vous souhaitez affecter à la section ; l'omission d'un caractère d'attribut provoque la désactivation du bit d'attribut.  Si vous ne spécifiez pas R, W ou E, l'état en lecture, écriture ou exécution existant reste inchangé.  
  
 Pour inverser l'effet d'un attribut, faites précéder son caractère d'un point d'exclamation \(\!\).  La signification des caractères d'attribut est illustrée ci\-après.  
  
|Caractère|Attribut|Signification|  
|---------------|--------------|-------------------|  
|E|Execute|La section est exécutable.|  
|R|Lire|Permet les opérations de lecture sur les données.|  
|W|Écriture|Permet les opérations d'écriture sur les données.|  
|S|Shared|Partage la section parmi tous les processus qui chargent l'image.|  
|D|Discardable \(peut être supprimé\)|Marque la section comme pouvant être supprimée.|  
|K|Cacheable \(peut être mis en mémoire cache\)|Marque la section comme ne pouvant pas être mise en mémoire cache.|  
|P|Pageable \(échangeable\)|Marque la section comme ne pouvant pas être échangeable.|  
  
 K et P sont particuliers en ce sens que les indicateurs de section correspondants sont dans le sens négatif.  Si vous spécifiez l'un d'entre eux dans la section .text \(\/SECTION:.text,K\), il n'y aura pas de différence dans les indicateurs de section lorsque vous exécuterez [DUMPBIN](../../build/reference/dumpbin-options.md) avec l'option [\/HEADERS](../../build/reference/headers.md) ; elle était déjà mise en cache de façon implicite.  Pour supprimer la valeur par défaut, spécifiez \/SECTION:.text,\!K, et DUMPBIN révélera les caractéristiques de section, y compris « Non mis en cache ».  
  
 Une section du fichier PE dont les attributs E, R ou W ne sont pas définis est probablement non valide.  
  
 ALIGN*\=\#* vous permet de spécifier une valeur d'alignement pour une section donnée.  Pour plus d'informations, consultez [\/ALIGN](../../build/reference/align-section-alignment.md).  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Ligne de commande**.  
  
4.  Tapez l'option dans la zone **Options supplémentaires**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)