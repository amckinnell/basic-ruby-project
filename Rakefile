require "rspec/core/rake_task"

require "reek/rake/task"
require "rubocop/rake_task"

RSpec::Core::RakeTask.new(:spec)

task default: [:spec, :rubocop, :reek]

desc "Run RuboCop"
RuboCop::RakeTask.new("rubocop") do |task|
  task.options = ["--display-cop-names"]
end

desc "Run Reek"
Reek::Rake::Task.new do |t|
  t.config_file   = ".reek"
  t.fail_on_error = true
  t.verbose = false
  t.source_files = "lib/**/*.rb"
end
