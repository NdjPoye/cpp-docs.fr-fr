---
title: "Allocation de piles | Microsoft Docs"
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
ms.assetid: 098e51f2-eda6-40d0-b149-0b618aa48b47
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Allocation de piles
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le prologue d'une fonction est chargé d'allouer l'espace de pile pour les variables locales, les registres enregistrés, les paramètres de pile et les paramètres de registre.  
  
 La zone de paramètres se situe toujours en bas de pile \(même si alloca est utilisé\), afin qu'elle soit toujours adjacente à l'adresse de retour pendant tout appel de fonction.  Elle comprend au moins quatre entrées, mais toujours suffisamment d'espace pour contenir tous les paramètres nécessaires à toute fonction susceptible d'être appelée.  Notez que de l'espace est toujours alloué pour les paramètres de registre, même si les paramètres proprement dits ne sont jamais hébergés dans la pile ; un appelé a la garantie que de l'espace a été alloué pour tous ses paramètres.  Les adresses d'origine des arguments de registre sont requises afin qu'une zone contiguë soit disponible au cas où la fonction appelée devrait prendre l'adresse de la liste d'arguments \(va\_list\) ou d'un argument particulier.  Cette zone fournit également un endroit commode pour l'enregistrement d'arguments de registre pendant l'exécution d'un thunk et comme option de débogage \(par exemple, elle permet de rechercher aisément les arguments pendant le débogage s'ils sont stockés à leur adresse d'origine dans le code de prologue\).  Même si la fonction appelée possède moins que 4 paramètres, ces 4 emplacements de pile sont en réalité détenus par la fonction appelée et peuvent être utilisés par celle\-ci à d'autres fins que l'enregistrement des valeurs du registre de paramètres.  Par conséquent, l'appelant ne peut pas enregistrer d'informations dans cette région de pile à l'aide d'un appel de fonction.  
  
 Si l'espace est alloué \(alloca\) dynamiquement dans une fonction, un registre non volatil doit être utilisé comme pointeur de frame pour marquer la base de la partie fixe de la pile et il doit être enregistré ainsi qu'initialisé dans le prologue.  Notez que lorsque alloca est utilisé, les appels au même appelé par le même appelant peuvent avoir des adresses d'origine différentes pour leurs paramètres de registre.  
  
 La pile est toujours alignée sur 16 octets, sauf dans le prologue \(par exemple, après l'exécution d'un push sur l'adresse de retour\) et à l'endroit indiqué dans [Types de fonctions](../build/function-types.md) pour une certaine classe de fonctions de trame.  
  
 Voici un exemple de la disposition de pile où la fonction A appelle une fonction B non\-feuille.  Le prologue de la fonction A a déjà alloué de l'espace pour tous les paramètres du registre et de pile que requiert B en bas de la pile.  L'appel effectue un push sur l'adresse de retour et le prologue de B alloue de l'espace pour ses variables locales et les registres non volatils, ainsi que l'espace dont il a besoin pour appeler des fonctions.  Si B utilise alloca, de l'espace est alloué entre la zone de sauvegarde des données de registre non volatiles\/variables locales et la zone de la pile de paramètres.  
  
 ![Exemple de conversion AMD](../build/media/vcamd_conv_ex_5.png "vcAmd\_conv\_ex\_5")  
  
 Lorsque la fonction B appelle une autre fonction, l'adresse de retour fait l'objet d'un push juste en dessous de l'adresse d'origine pour RCX.  
  
## Voir aussi  
 [Utilisation de la pile](../build/stack-usage.md)