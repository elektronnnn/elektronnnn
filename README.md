import random

# Function to generate a random number with a known seed
def generate_random_number(seed):
    random.seed(seed)
    return random.randint(1, 100)  # Generates a number between 1 and 100

# Function to brute-force the seed by matching the random number
def brute_force_seed(target_number):
    # We know the range of seeds we're interested in (for example, from 0 to 100,000)
    for seed in range(0, 100000):
        if generate_random_number(seed) == target_number:
            return seed
    return None

# Example usage
# Known seed
correct_seed = 12345
# Generate the random number with the known seed
target_number = generate_random_number(correct_seed)

print(f"Generated random number with seed {correct_seed}: {target_number}")

# Now try to brute-force the seed
brute_forced_seed = brute_force_seed(target_number)

if brute_forced_seed is not None:
    print(f"Brute-forced the correct seed: {brute_forced_seed}")
else:
    print("Could not find the seed.")
