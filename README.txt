DESCRIPTION

  This is a collection of datasets built at increasing levels of complexity, aimed
  at iteratively building and evaluating recognizers from scratch.

  Images are all 100x100, in 4 levels of complexity: very easy, easy, medium and
  hard. See the README files inside the respective folders for the details.


SOURCES

  We have used images from several sources: mainly a modified subset of the FEI face image
  dataset part 1, as well as cropped regions detected by Facebook on arbitrary
  photos.


FILE NAMES

  Files are named in an uniform manner as follows

  <person number id>-<person photo-id>.{jpg,png}

  Example: 17-3.jpg means photo number 3 of person number 17.

  The mapping onto the original database image filenames is presented in a text
  file for each dataset (eg, FEI Face database)


ITERATIVELY DEVELOPING A RECOGNITION ALGORITHM

  1. Starting at the very-easy folder, write routines to read the image files
  into 2D arrays of pixels, and organize these into a list of 1D vectors of pixels

  2. Write the simplest possible recognizer by direct image similarity (norm of image
  difference)

  3. Write a cross-validation for your initial simple classifier. 
  3.1 Separate your images into test and training sets
  3.2 Output a recognition score and running time. 

  4. Attempt to modify the way you compute the similarity in (2) as to increse
  the recognition score

  5. Implement simple linear techniques such as PCA
  5.1 stack the image vectors as columns of a data matrix
  5.2 optionally subtract the mean vector from each column
  5.3 compress the matrix using svd to n dimension using the top n singular values
  5.4 project each new image to the space of columns in the matrix
  5.5 compare image similarity based on: 
  5.5.1 distance between reduced dimension vectors
  5.5.2 projection distance to each subspace of each face
  5.5.3 distance between reconstructed vectors. do you get better quality? how
        about the drop in speed? is it significant?
  5.6 change n in (5.3)      
  5.7 output recognition rates for each change you make.
  
  7. Run your benchmarks on the very-easy dataset
  
  8. Fine tune your algorithm and study failure cases. 
  
  9. Try to scale your code to the medium dataset 
  
  10. Implement a more complicated technique. Output recognition rates as you go. 
  
  11. Scale your algorithm to the hard dataset
  
  12. Try the remaining datasets at extras/, possibly before going to the hard
  dataset


AUTHOR
  Curated by Ricardo Fabbri (rfabbri at gmail) - IPRJ/UERJ Nova Friburgo
