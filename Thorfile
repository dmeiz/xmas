class Xmas < Thor
  desc 'resize', 'Resize images in original_images to public'
  def resize
    Dir.glob('original_images/*.jpg').each do |original_image|
      system "convert -resize 400 #{original_image} public/#{File.basename(original_image)}"
    end
  end
end
