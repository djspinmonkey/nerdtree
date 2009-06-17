PLUGIN_DIR = File::expand_path("~/.vim/plugin")
DOC_DIR    = File::expand_path("~/.vim/doc")

directory PLUGIN_DIR
directory DOC_DIR

desc "Copy the vim/doc files into ~/.vim"
task :deploy_local => [ PLUGIN_DIR, DOC_DIR ] do
  run "cp plugin/NERD_tree.vim #{PLUGIN_DIR}"
  run "cp doc/NERD_tree.txt #{DOC_DIR}"
end

desc "Create a zip archive for release to vim.org"
task :zip do
  abort "NERD_tree.zip already exists, aborting" if File.exist?("NERD_tree.zip")
  run "zip NERD_tree.zip plugin/NERD_tree.vim doc/NERD_tree.txt"
end

def run(cmd)
  puts "Executing: #{cmd}"
  system cmd
end

