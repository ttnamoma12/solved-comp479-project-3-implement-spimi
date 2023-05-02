Download Link: https://assignmentchef.com/product/solved-comp479-project-3-implement-spimi
<br>
<strong>Objectives: </strong>Implement SPIMI. Implement ranking of returns. Test and analyze your system, discuss how your design decisions influence the results.

<strong>Data: </strong>Use Reuters21578 for testing and if needed, continue your text scrubbing skills for the final project. Note that the text preprocessing should be secondary in this project.

<strong>Description: </strong>this project consists of two subprojects that build on each other. Each subproject should be very simple to execute, discuss with your peers and during Lab Q&amp;A if there are any hurdles.

<strong>Subproject I:            </strong>Implement SPIMI using your Project 2 Subproject 1 system. In particular:

<ol>

 <li>(Project 2 Subproject I item 1:) develop a module that while there are still more documents to be processed, accepts a document as a list of tokens and outputs term-documentID pairs. Instead of appending new termdocID pairings <strong>(since you are not to compress the index, a matched token and docID, not a pair data structure. Omit punctuation.) </strong>to a global list, do:</li>

 <li>SPIMI:

  <ul>

   <li>in the following, replace <em>K </em>with 500 for submitting your first and last block for grading</li>

   <li>replace <em>K </em>with 10000 for comparison with naive indexer</li>

  </ul></li>

</ol>

for <em>K </em>term-docIDs, create a new hash key for the term if necessary and/or append the docID to the postings list associated with the hashed term <strong>if it is not already listed in the postings list or if it is already listed, augment a term counter to calculate </strong><em>tf</em><strong>.</strong>

<ol start="3">

 <li>when the block is full (representing <em>K </em>term-docIDs), collect the index, sort, and ”store” in consecutively labelled BlockX</li>

 <li>disk block merging: when all term-docID pairs of your input are stored in block-sized indices, merge the miniindeces into a global index. You can hold the merged index in memory</li>

 <li>compare timing with the naive indexer <strong>(for 10000 term-docID pairings).</strong></li>

 <li>compile an inverted index for Reuters21578 without using any compression techniques<strong>docID hint: </strong>Use the NEWID values from the Reuters corpus to make your retrieval comparable.</li>

</ol>

<strong>Subproject II:          </strong>Convert your indexer into a probabilistic search engine

<ol>

 <li>using the assumptions made in Chapter 11 about independence of terms and documents etc. and</li>

 <li>using the BM25 formula (11.32),</li>

 <li>rank the documents your SPIMI implementation returns and</li>

 <li>for a given query, return a ranked list of results.</li>

</ol>

<strong>Notes:         </strong>experiment with different values for the parameters <em>k</em><sub>1 </sub>and <em>b </em>as described in the textbook.

<strong>Test queries:</strong>

<ol>

 <li>design <strong>four </strong>test queries:

  <ul>

   <li>a single keyword query, <strong>to comapre with Project 2</strong></li>

   <li><strong>a query consisting of several keywords for BM25</strong></li>

   <li>a multiple keyword query returning documents containing all the keywords (AND), <strong>for unranked Boolean retrieval</strong></li>

   <li>a multiple keywords query returning documents containing at least one keyword (OR), where documentsare ordered by how many keywords they contain), <strong>for unranked Boolean retrieval</strong></li>

  </ul></li>

 <li>run your <strong>four </strong>test queries to showcase your code and comment on the results in your report <strong>Deliverables:</strong></li>

 <li>individual project</li>

 <li>well documented code</li>

 <li>well documented sample runs for your queries on the information needs:

  <ul>

   <li>Democrats’ welfare and healthcare reform policies</li>

   <li>Drug company bankruptcies</li>

   <li>George Bush</li>

  </ul></li>

 <li>any additional testing or aborted design ideas that show off particular aspects of your project</li>

</ol>

a project report that summarizes your approach, illustrates your design and discusses what you have learnedfrom the project. Note that a summary and commentary on your sample runs has to be included in the report