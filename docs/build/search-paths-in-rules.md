---
title: "Chemins de recherche utilis&#233;s dans les r&#232;gles | Microsoft Docs"
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
  - "règles d'inférence dans NMAKE"
  - "règles, inférence"
  - "chemins de recherche dans les règles d'inférence NMAKE"
ms.assetid: 38feded6-536d-425d-bf40-fff3173a5506
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Chemins de recherche utilis&#233;s dans les r&#232;gles
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

```  
{frompath}.fromext{topath}.toext:  
   commands  
```  
  
## Remarques  
 Une règle d'inférence s'applique à une dépendance seulement si les chemins spécifiés dans la dépendance correspondent exactement aux chemins des règles d'inférence.  Spécifiez le répertoire du dépendant dans *frompath* et le répertoire de la cible dans *topath* ; les espaces ne sont pas admis.  Spécifiez un seul chemin pour chaque extension.  Un chemin sur une extension exige un chemin sur l'autre.  Pour spécifier le répertoire actif, utilisez soit un point \(.\), soit des accolades vides \({ }\).  Les macros peuvent représenter *frompath* et *topath* ; elles sont appelées pendant le prétraitement.  
  
## Exemple  
  
### Code  
  
```  
{dbi\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $(YUDBI) $<  
  
{ilstore\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $<  
  
{misc\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $(YUPDB) $<  
  
{misc\}.c{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $<  
  
{msf\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $<  
  
{bsc\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $(YUPDB) $<  
  
{mre\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $(YUPDB) $<  
  
{namesrvr\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $(YUPDB) $<  
  
{src\cvr\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $<  
```  
  
## Voir aussi  
 [Définition d'une règle](../build/defining-a-rule.md)