load './platform/Rakefile'


class Rake::Task

  def overwrite(&block)
    @actions.clear
    prerequisites.clear
    enhance(&block)
  end

  def abandon
    @actions.clear
    prerequisites.clear
  end

end


Rake::Task["x"].enhance do
  Rake::Task["extra"].invoke
end

Rake::Task["y"].overwrite do
  Rake::Task["replace"].invoke
end

Rake::Task["z"].abandon

Rake::Task.new(:z) do |t|
	t.verbose = true
end




task (:extra) { puts "This is extra text" }
task (:replace) { puts "This is replacement of original task" }



# http://blog.jayfields.com/2008/02/rake-task-overwriting.html
#
