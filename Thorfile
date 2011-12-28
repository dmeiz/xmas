class Xmas < Thor
  desc 'resize', 'Resize images in original_images to public; export files from iPhoto with sequential file names to original_images'
  def resize
    system('rm public/images/*')
    Dir.glob('original_images/*.jpg').each do |original_image|
      system "convert -resize 400 #{original_image} public/images/#{File.basename(original_image)}"
    end
  end

  desc 'upload_images', 'Upload images from public/images to server'
  def upload_images
    system('rsync -av public/images/ dev@transfer03.methodhead.com:/u/apps/xmas/shared/images/')
  end
end
