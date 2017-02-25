---
title: "Vue d&#39;ensemble des conventions d&#39;appel x64 | Microsoft Docs"
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
ms.assetid: a05db5eb-0844-4d9d-8b92-b1b2434be0ea
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Vue d&#39;ensemble des conventions d&#39;appel x64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Deux des modifications importantes du passage de x86 à [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] sont la fonction d'adressage 64 bits et un jeu de 16 registres 64 bits pour une utilisation générale.  Étant donné le jeu de registres étendu, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] utilise uniquement la convention d'appel [\_\_fastcall](../cpp/fastcall.md) et un modèle de gestion des exceptions basé sur RISC.  Le modèle `__fastcall` utilise des registres pour les quatre premiers arguments et le frame de pile pour passer les autres paramètres.  
  
 L'option du compilateur suivante vous aide à optimiser votre application pour [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] :  
  
-   [\/favor \(optimisation pour les particularités d'architecture\)](../build/reference/favor-optimize-for-architecture-specifics.md)  
  
## Convention d'appel  
 L'interface binaire d'application \(ABI\) [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] est une convention d'appel rapide à 4 registres, avec un stockage de pile pour ces registres.  Il existe une stricte correspondance un à un entre les arguments d'une fonction et les registres de ces arguments.  Tout argument qui ne rentre pas sur 8 octets, ou qui n'est pas à 1, 2, 4 ou 8 octets, doit être passé par référence.  Il n'y a aucune tentative visant à répartir un argument unique sur plusieurs registres.  La pile du registre x87 est inutilisée.  Elle peut être utilisée, mais doit être considérée comme volatile à travers les appels de fonction.  Toutes les opérations en virgule flottante sont effectuées à l'aide des 16 registres XMM.  Les arguments sont passés dans les registres RCX, RDX, R8 et R9.  Si les arguments sont float\/double, ils sont passés dans XMM0L, XMM1L, XMM2L et XMM3L.  Les arguments à 16 octets sont passés par référence.  Le passage de paramètres est décrit en détail dans [Passage de paramètres](../build/parameter-passing.md).  Outre ces registres, RAX, R10, R11, XMM4 et XMM5 sont volatiles.  Tous les autres registres sont non volatiles.  L'utilisation des registres est documentée en détail dans [Utilisation des Registres](../build/register-usage.md) et [Registres enregistrés des appelants\/appelés](../build/caller-callee-saved-registers.md).  
  
 L'appelant est chargé d'allouer de l'espace pour les paramètres de l'appelé et doit toujours allouer un espace suffisant pour les 4 paramètres de registre, même si l'appelé n'a pas autant de paramètres.  Cela contribue à la simplicité de la prise en charge des fonctions non prototypées C, et des fonctions vararg C\/C\+\+.  Pour les fonctions vararg ou non prototypées, toutes les valeurs float doivent être dupliquées dans le registre généraliste correspondant.  Tous les paramètres au\-dessus des 4 premiers doivent être stockés sur la pile, au\-dessus du magasin de stockage des 4 premiers, avant l'appel.  Les fonctions Vararg sont décrites en détail dans [Varargs](../build/varargs.md).  Des informations détaillées sur les fonctions non prototypées se trouvent dans [Fonctions non prototypées](../build/unprototyped-functions.md).  
  
## Alignement  
 La plupart des structures sont alignées sur leur alignement naturel.  Les principales exceptions sont le pointeur de pile et la mémoire malloc ou alloca, qui sont alignés sur 16 octets pour de meilleures performances.  Un alignement supérieur à 16 octets doit se faire manuellement, mais puisque 16 octets sont une taille d'alignement courante pour les opérations XMM, cela devrait suffire pour l'essentiel du code.  Pour plus d'informations sur la disposition et l'alignement de la structure, consultez [Types et stockage](../build/types-and-storage.md).  Pour plus d'informations sur la disposition de la pile, consultez [Utilisation de la pile](../build/stack-usage.md).  
  
## Capacité de déroulement  
 Toutes les fonctions feuilles \[fonctions qui n'appellent pas de fonction et n'allouent pas d'espace de pile\] doivent être annotées avec des données \[connues sous le nom de xdata ou ehdata, pointées par pdata\] qui décrivent au système d'exploitation comment les dérouler correctement, pour récupérer les registres non volatiles.  Les prologues et épilogues sont extrêmement restreints, afin de pouvoir être décrits correctement dans xdata.  Le pointeur de pile doit être aligné sur 16 octets, sauf pour les fonctions feuilles, dans les parties du code qui ne font pas partie d'un épilogue ou d'un prologue.  Pour plus d'informations sur la structure appropriée des prologues et des épilogues de fonction, consultez [Prologue et épilogue](../build/prolog-and-epilog.md).  Pour plus d'informations sur la gestion des exceptions et sur les pdata et xdata dans la gestion des exceptions ou leur déroulement, consultez [Gestion des exceptions \(x64\)](../build/exception-handling-x64.md).  
  
## Voir aussi  
 [Conventions des logiciels x64](../build/x64-software-conventions.md)