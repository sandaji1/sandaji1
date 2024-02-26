from PIL import Image, ImageDraw, ImageFont

# Define image size and background color
width = 800
height = 400
background_color = (255, 255, 255)  # White background

# Create a new image with white background
image = Image.new("RGB", (width, height), background_color)
draw = ImageDraw.Draw(image)

# Define colors from the tricolor of India
saffron = (255, 153, 51)  # Saffron color
green = (18, 136, 7)  # Green color
navy_blue = (0, 32, 96)  # Navy blue color

# Draw a rectangle for saffron color
saffron_height = height // 3
draw.rectangle([0, 0, width, saffron_height], fill=saffron)

# Draw a rectangle for white color (to create space for text)
white_height = height // 3
draw.rectangle([0, saffron_height, width, saffron_height*2], fill=(255, 255, 255))

# Draw a rectangle for green color
green_height = height // 3
draw.rectangle([0, saffron_height*2, width, height], fill=green)

# Define tagline text and font
tagline = "Numbers that Define, Progress that Unites"
font_path = "path_to_your_font_file.ttf"  # Replace with your font file path
font_size = 36
font = ImageFont.truetype(font_path, font_size)

# Calculate text size and position
text_width, text_height = draw.textsize(tagline, font=font)
text_x = (width - text_width) // 2
text_y = (height - text_height) // 2

# Draw tagline text
draw.text((text_x, text_y), tagline, font=font, fill=navy_blue)

# Save the image
image.save("patriotic_tagline_image.png")

# Display the image
image.show()
