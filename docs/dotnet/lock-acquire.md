---
title: "lock::acquire | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "lock::acquire"
  - "acquire"
  - "msclr.lock.acquire"
  - "msclr::lock::acquire"
  - "lock.acquire"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "acquire (méthode)"
ms.assetid: c214274e-7519-4739-82aa-91b04a32d3f9
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# lock::acquire
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Construit un verrou sur un objet , en attendant éventuellement d'acquérir le verrou soit indéfiniment, soit pour une durée spécifiée, soit pas du tout.  
  
## Syntaxe  
  
```  
void acquire();  
void acquire(  
   int _timeout  
);  
void acquire(  
   System::TimeSpan _timeout  
);  
```  
  
#### Paramètres  
 `_timeout`  
 Valeur du délai d'attente en millisecondes ou en tant que <xref:System.TimeSpan>.  
  
## Exceptions  
 Lève <xref:System.ApplicationException> si l'acquisition du verrou n'a pas lieu avant le délai d'attente.  
  
## Notes  
 Si une valeur de délai d'attente n'est pas fournie, l'intervalle par défaut est <xref:System.Threading.Timeout.Infinite>.  
  
 Si un verrou a déjà été acquis, cette fonctionnalité n'a aucun effet.  
  
## Exemple  
 Cet exemple utilise une seule instance d'une classe entre des threads multiples.  La classe utilise un verrou sur elle\-même pour garantir que les accès à ses données internes sont cohérents pour chaque thread.  Le thread d'application principale utilise un verrou sur la même instance de la classe pour vérifier régulièrement si les threads de travail existent toujours, et attend pour quitter jusqu'à ce que tous les threads de travail aient terminé leurs tâches.  
  
```  
// msl_lock_acquire.cpp  
// compile with: /clr  
#include <msclr/lock.h>  
  
using namespace System;  
using namespace System::Threading;  
using namespace msclr;  
  
ref class CounterClass {  
private:  
   int Counter;     
  
public:  
   property int ThreadCount;  
  
   // function called by multiple threads, use lock to keep Counter consistent  
   // for each thread  
   void UseCounter() {  
      try {  
         lock l(this); // wait infinitely  
  
         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,   
            Counter);  
  
         for (int i = 0; i < 10; i++) {  
            Counter++;  
            Thread::Sleep(10);  
         }  
  
         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,   
            Counter);  
  
         Counter = 0;  
         // lock is automatically released when it goes out of scope and its destructor is called  
      }  
      catch (...) {  
         Console::WriteLine("Couldn't acquire lock!");  
      }  
  
      ThreadCount--;  
   }  
};  
  
int main() {  
   // create a few threads to contend for access to the shared data  
   CounterClass^ cc = gcnew CounterClass;  
   array<Thread^>^ tarr = gcnew array<Thread^>(5);  
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);  
   for (int i = 0; i < tarr->Length; i++) {  
      tarr[i] = gcnew Thread(startDelegate);  
      cc->ThreadCount++;  
      tarr[i]->Start();  
   }  
  
   // keep our main thread alive until all worker threads have completed  
   lock l(cc, lock_later); // don't lock now, just create the object  
   while (true) {  
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't  
         if (0 == cc->ThreadCount) {  
            Console::WriteLine("All threads completed.");  
            break; // all threads are gone, exit while  
         }  
         else {  
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);  
            l.release(); // some threads exist, let them do their work  
         }  
      }  
   }  
}  
```  
  
  **Dans le thread 3, Compteur \= 0**  
**Dans le thread 3, Compteur \= 10**  
**Dans le thread 5, Compteur \= 0**  
**Dans le thread 5, Compteur \= 10**  
**Dans le thread 7, Compteur \= 0**  
**Dans le thread 7, Compteur \= 10**  
**Dans le thread 4, Compteur \= 0**  
**Dans le thread 4, Compteur \= 10**  
**Dans le thread 6, Compteur \= 0**  
**Dans le thread 6, Compteur \= 10**  
**Tous les threads sont terminés.**   
## Configuration requise  
 **Fichier d'en\-tête** \<msclr\\lock.h\>  
  
 **Espace de nommage** msclr  
  
## Voir aussi  
 [lock, membres](../dotnet/lock-members.md)   
 [lock::try\_acquire](../dotnet/lock-try-acquire.md)