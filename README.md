# P2F
The project aimes to protect the miners wallets from scammers by providing unique authenticator code for each wallets transaction on the wallet before processing it to increase the security layers for our valuable pi coins and avoid getting stollen
import pyotp

# Generate a secret key for the user
secret_key = pyotp.random_base32()

# Create a TOTP object using the secret key
totp = pyotp.TOTP(secret_key)

# Get the current OTP
current_otp = totp.now()

# Print the current OTP
print("Current OTP:", current_otp)

# Verify an OTP
user_input = input("Enter OTP to verify: ")
is_valid = totp.verify(user_input)

if is_valid:
    print("OTP is valid")
else:
    print("OTP is not valid")
