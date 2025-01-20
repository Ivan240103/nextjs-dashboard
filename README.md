# Next.js App Router Course - Starter

This is the starter template for the Next.js App Router Course. It contains the starting code for the dashboard application.

For more information, see the [course curriculum](https://nextjs.org/learn) on the Next.js Website.

## Index
1. **Getting Started**  
  Creazione dell'app con `create-next-app` ed introduzione alla struttura del progetto.
2. **CSS Styling**  
  *Global styles* legati al RootLayout, *Tailwind* e *CSS Modules* per la personalizzazione, `clsx` per la personalizzazione condizionale.
3. **Optimizing Fonts and Images**  
  Modulo `next/font` per ottimizzare il caricamento dei font, modulo `next/image` per ottimizzare le immagini tramite il tag `<Image />`.
4. **Creating Layouts and Pages**  
  *File-System routing* per creare i path basati sulla struttura delle cartelle. `layout.tsx` mantiene la UI condivisa tra più pagine, `page.tsx` permette di rendere una route accessibile. Ogni app deve avere un layout come top-level: il *RootLayout*. Tramite il *partial rendering* si renderizza solo il contenuto delle pagine interne al layout anziché l'intera schermata.
5. **Navigating Between Pages**  
  Modulo `next/link` per la navigazione client-side usando il tag `<Link />`. Tramite esso non viene ricaricata l'intera schermata al click e avviene il pre-fetch lato server delle pagine quando *<Link />* entra nella viewport.
6. **Setting Up Your Database**  
  Utilizzo di Vercel per hostare un database Postgres e fare il deploy automatico da GitHub.
7. **Fetching Data**  
  Per il fetch dei dati da un db usare un *API layer* intermedio oppure eseguire le query direttamente da un componente server. Funzione `sql` fornita da Vercel per effettuare le query. Lo *static rendering* impedisce l'aggiornamento della schermata in tempo reale. Se possibile, effettuare il fetch in parallelo usando `Promise.all([...])`.
8. **Static and Dynamic Rendering**  
  *Static rendering* velocizza il sito, riduce il carico del server e migliora l'indicizzazione SEO. *Dynamic rendering* si usa quando bisogna mostrare dati in tempo reale, dati specifici per l'utente o quando servono informazioni note soltanto a request time. Con quest'ultimo l'applicazione è veloce quanto il fetch più lento.
9. **Streaming**  
  Lo *streaming* permette di caricare i dati dal server "a pezzi" e usarli nell'app man mano che diventano disponibili. `loading.tsx` per definire un fallback per l'intera pagina mentre i dati si caricano. `<Suspense>` per wrappare un componente e definire un fallback solo per esso. Uno *skeleton* è una visualizzazione di attesa che fa intendere il caricamento dei dati. `/(folder)` crea un *route group*, il cui nome viene ignorato nel routing, per separare logicamente i file. Buona prassi usare *Suspense* con i singoli componenti che lo necessitano.
10. **Partial Prerendering**
  Il *partial prerendering* consente di combinare rendering statico e dinamico in una stessa route. Si implementa wrappando le componenti dinamiche con i `<Suspense />`, previa attivazione della configurazione *ppr*.
11. **Adding Search and Pagination**
  Effettuare le ricerche nel db e la paginazione dei dati usando gli URL invece che gli state, tramite gli hook `useSearchParams` per i parametri, `usePathname` per il path corrente e `useRouter` per la navigazione. `URLSearchParams` = oggetto per gestire i parametri delle query. Implementazione *debounce* per eseguire la ricerca solo quando l'utente smette di digitare.
12. **Mutating Data**
  Le *React Server Actions* servono per implementare funzioni asincrone direttamente sul server. Libreria `zod` per fare type validation. Funzione `revalidatePath()` per aggiornare la cache del client. Funzione `redirect()` da `next/navigation` per reindirizzare il client tramite l'URL. `/[folder]` crea una route dinamica, il cui nome compare nel routing. `params` nei props per accedere gli elementi dinamici della route.
13. **Handling Errors**
  File speciale `error.tsx` per avere un fallback in caso di eccezioni non catturate (deve essere un *client component*). Funzione `notFound()` da `next/navigation` per mostrare un fallback specifico per gli errori 404, definito nel file `not-found.tsx`.

## Participants
Ivan De Simone
