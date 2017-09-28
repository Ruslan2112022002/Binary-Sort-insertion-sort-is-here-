# Binary-Sort-insertion-sort-is-here-
Сортировка для инфы

#include "txLib.h"

int const DATA_SIZE = 50;


void fill  (int data [],int size);
void print (int const data [], int size);
int binary_search (int const data [], int number_to_swap);
void ROR (int data [], int start, int last_number);
void sort (int data [], int size);
int search_position (int const data [], int number_to_swap);



int main ()

    {

    int data [DATA_SIZE] = {};
    fill (data, DATA_SIZE);
    sort (data, DATA_SIZE);
    //Print (data, DATA_SIZE);
    // ROR (data, 0, DATA_SIZE-1);
    print (data, DATA_SIZE);
    }



void sort (int data [], int size)

    {

    if (data [0] > data [1])
        {

        int a = data[0];
        data [0] = data [1];
        data [1] = a;

        }

    for (int i = 2; i < size ; i++)

        {

        ROR (data, binary_search (data, i), i );

        }

    }


void fill (int data [],int size)

    {

    srand (GetTickCount());

    for (int i = 0; i < size; i++)

        {

        data [i] = rand ();

        }

    }

void print (int const data [], int size)

    {

    for (int i = 0; i < size; i++)

        {

        printf ("data [%d] = %d \n", i, data [i]);

        }

    }

int binary_search (int const data [], int number_to_swap)

  {

  /*    int right = number_to_swap;
    int left = 0;

    while(right - left > 3)
        {

        int i = (right + left) / 2;
        if(data [i] > number_to_swap)
            right = i;

        else
            left = i;

        }


    return (right + left) / 2;

    }  */

    int right = number_to_swap;
    int left = 0;
    while(right - left > 3)

        {

        int i = floor((right + left) / 2);
        if(data[i] > data [number_to_swap])
            {

            right = i;

            }
        else

            {

            left = i;

            }

        }

    for (int i = left; i < right; i++)

        {

        if (data[i] > data[number_to_swap])

            {

            return i;

            }

        return right;

        }

    }


void ROR (int data [], int start, int last_number)

    {

    int first_number = data [last_number];

    for (int i = last_number; i > start; i --)

        {

        data [i] = data [i - 1];

        }

    data [start] = first_number;

    }

int search_position (int const data [], int number_to_swap)

    {

    for (int i = 0; i < number_to_swap; i ++)

        {

        if (data [i] > data[number_to_swap])

            {

            return i;

            }

        }

    }


