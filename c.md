## Debug

    # include <time.h>

	clock_t begin = clock();

	action_to_time();

	clock_t end = clock();
	double time_spent = (double)(end - begin) / CLOCKS_PER_SEC;
	printf("time spent: %f\n", time_spent);