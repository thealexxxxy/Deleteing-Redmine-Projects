#! ruby -Ks
# coding: utf-8

require 'rubygems'
require 'active_record'


# DBに書き込み時のtimezoneの設定
ActiveRecord::Base.default_timezone = :local

#DBに接続
ActiveRecord::Base.establish_connection(
            :adapter  => 'mysql',
            :host     => 'localhost',
            :username => 'hogehoge',
            :password => 'hogehoge',
            :database => 'hogehoge'
)

# projects
class Project < ActiveRecord::Base
end

# attachments
class Attachment < ActiveRecord::Base
end

# issues
class Issue < ActiveRecord::Base
end

# newss
class News < ActiveRecord::Base
end

# versions
class Version < ActiveRecord::Base
end

# documents
class Document < ActiveRecord::Base
end

# wiki_pages
class Wiki_page < ActiveRecord::Base
end

# wikis
class Wiki < ActiveRecord::Base
end

# journals
class Journal < ActiveRecord::Base
end

# issue_categories
class Issue_category < ActiveRecord::Base
end

# members
class Member < ActiveRecord::Base
end

# queries
class Query < ActiveRecord::Base
end

# repositories
class Repository < ActiveRecord::Base
self.inheritance_column = :_type_disabled 
end

# time_entries
class Time_entry < ActiveRecord::Base
end

#### 更新期限の設定
from = Time.now
#to   = from - 6.month
to   = from - 2.year

project_all = []
project_result = []
update_project = []
update_project_id = []
update_project_all = []
update_project_issue = []
update_project_news = []
update_project_version = []
update_project_document = []
update_project_wiki_page = []
update_parent_id = []


## 除外後の削除プロジェクト
project_result_exclude = []


########## issue update ############
##  Issue_table
issues = Issue.where("updated_on > ?",to)
  issues.each do |issue|
    update_project_issue << issue.project_id
  end

#### attach_table_issue
attach_issues = Attachment.where("container_type = ? and created_on > ?", "Issue",to) 
    attach_issues.each do |attach_issue|
    issues2 = Issue.where(:id => "#{attach_issue.container_id}")
      issues2.each do |issue2|
      update_project_issue << issue2.project_id
  end
end

#print "# update project_id_issue "
#print "\n"
#print update_project_issue.uniq
#print "\n"
#print "\n"

########## news update ############
newss = News.where("created_on > ?",to)
   newss.each do |news|
   update_project_news << news.project_id
 end


#print "# update project_id_news "
#print "\n"
#print update_project_news.uniq
#print "\n"
#print "\n"

########## version update ############
versions = Version.where("updated_on > ?",to)
   versions.each do |version|
     update_project_version << version.project_id
   end

#### attach_table_version
attach_versions = Attachment.where("container_type = ? and created_on > ?", "Version",to)
    attach_versions.each do |attach_version|
    versions2 = Version.where(:id => "#{attach_version.container_id}")
      versions2.each do |version2|
      update_project_version << version2.project_id
  end
end

#print "# update project_id_version "
#print "\n"
#print update_project_version.uniq
#print "\n"
#print "\n"

########## document update ############
documents = Document.where("created_on > ?",to)
   documents.each do |document|
     update_project_document << document.project_id
   end

#### attach_table_document
attach_documents = Attachment.where("container_type = ? and created_on > ?", "Document",to)
    attach_documents.each do |attach_document|
    documents2 = Document.where(:id => "#{attach_document.container_id}")
      documents2.each do |document2|
      update_project_document << document2.project_id
  end
end

#print "# update project_id_document "
#print "\n"
#print update_project_document.uniq
#print "\n"
#print "\n"

########## wiki_page update ############
wiki_pages = Wiki_page.where("created_on > ?",to)
     wiki_pages.each do |wiki_page|
          #### wilki_id → priject_id へ変換
          wikis = Wiki.where(:id => "#{wiki_page.wiki_id}")
          wikis.each do |wiki|
          update_project_wiki_page << wiki.project_id
   end
end

#### attach_wiki_page
attach_wiki_pages = Attachment.where("container_type = ? and created_on > ?", "Wiki_page",to)
    attach_wiki_pages.each do |attach_wiki_page|
    wiki_pages2 = Wiki_page.where(:id => "#{attach_wiki_page.container_id}")
      wiki_pages2.each do |wiki_page2|
      update_project_wiki_page << wiki_page2.project_id
  end
end

#print "# update project_id_wiki_page "
#print "\n"
#print update_project_wiki_page.uniq
#print "\n"
#print "\n"

########## project update ############
projects = Project.where("updated_on > ?",to)
   projects.each do |project|
     update_project_id << project.id
   end


######### 配列をまとめる

update_project = update_project_issue.uniq | update_project_news.uniq | update_project_version.uniq | update_project_document.uniq | update_project_wiki_page.uniq | update_project_id
#print "# update project_id_all"
#print "\n"
#print update_project
#print "\n"
#print "\n"

###### parent_idの抽出
update_project.each do |update_project_c|
    projects2 = Project.where(:id => "#{update_project_c}")
    projects2.each do |project2|
      if project2.parent_id != nil
       update_parent_id << project2.parent_id
     end
    end
end

#print "# update parent_id "
#print "\n"
#print update_parent_id.uniq
#print "\n"
#print "\n"

########## project_all ############
projects = Project.all
   projects.each do |project|
     project_all << project.id
   end
#print "# project_all_id "
#print "\n"
#print project_all.uniq
#print "\n"
#print "\n"

#print "\n"
#print "# Not update project_result"
#print "\n"
update_project_all = update_project|update_parent_id.uniq
project_result = project_all - update_project_all
#print project_result
#print "\n"
#print "\n"

#print "\n"
#print "\n"
########## Be not updated project_name #########

###　こちらの内容をメールで送信する。

print " ***** 2年以上更新されていないProject ****"
     print "\n"
     project_result.each do |not_update_project|
     not_update_projects = Project.where(:id => "#{not_update_project}")
     not_update_projects.each do |not_update_project2|

#     print not_update_project2.id
#     print "\t"
     print not_update_project2.name
     print "\n"
    end
end
print "*****"
print "\n"

######## project_nameを削除しない場合はこちらで省くようにする #######
#print "\n"
#print "##### 6ヶ月以上更新されていないproject(除外後) ######"
#print "\n"
  project_result.each do |not_update_project|
     not_update_projects = Project.where(:id => "#{not_update_project}")
     not_update_projects.each do |not_update_project2|

     ######## //に除外sitaProject名を書く
     # ex.)
     # /プロジェクト名/
     #
  
     if /aa/ !~ not_update_project2.name
#         print not_update_project2.id
#       print "\t"
#         print not_update_project2.name
#       print "\n"
project_result_exclude << not_update_project2.id         
    end
   end
 end
 
#print "\n"
#print "\n"
            
##########  削除するProjectに関連するデータ  ##########
# 
# 削除するProject_IDは、「project_result_exclude」を使う
# 

issue_delete_id = []
version_delete_id = []
document_delete_id = []
wiki_page_delete_id = []
attachment_disk_filename = []

##### Issue #####

#print "\n"
#print "# 削除するissue (id,subject) "
#print "\n"
 project_result_exclude.each do |not_update_project|
    issues = Issue.where(:project_id => "#{not_update_project}")
     issues.each do |issue|
#   print issue.id
#   print "\t"
#   print issue.subject
#print "\n"
   issue_delete_id << issue.id
  end
end

##### News #####

#print "\n"
#print "# 削除するnews (id,title) "
#print "\n"
 project_result_exclude.each do |not_update_project|
    newss = News.where(:project_id => "#{not_update_project}")
     newss.each do |news|
#   print news.id
#   print "\t"
#   print news.title
#print "\n"
  end
end

##### Version #####

#print "\n"
#print "# 削除するversion (id,title) "
#print "\n"
 project_result_exclude.each do |not_update_project|
    versions = Version.where(:project_id => "#{not_update_project}")
     versions.each do |version|
#   print version.id
#   print "\t"
#   print version.name
#print "\n"
    version_delete_id << version.id
  end
end

##### Document #####

#print "\n"
#print "# 削除するdocument (id,title) "
#print "\n"
 project_result_exclude.each do |not_update_project|
    documents = Document.where(:project_id => "#{not_update_project}")
     documents.each do |document|
#   print document.id
#   print "\t"
#   print document.title
#print "\n"
    document_delete_id << document.id
  end
end

##### Wiki_Page #####

#print "\n"
#print "# 削除するWiki_Page (id,title) "
#print "\n"
 project_result_exclude.each do |not_update_project|
      wikis = Wiki.where(:project_id => "#{not_update_project}")
        wikis.each do |wiki|
        wiki_pages = Wiki_page.where(:wiki_id => "#{wiki.id}")
        wiki_pages.each do |wiki_page|
#    print wiki_page.id
#    print "\t"
#    print wiki_page.title
#    print "\n"
    wiki_page_delete_id << wiki_page.id
      end
   end
end

##### Journal #####
# journalはproject_idではなく、issueの削除IDから抽出する

#print "\n"
#print "# 削除するjournals (id,journalized_id,journalized_type) "
#print "\n"
 issue_delete_id.each do |not_update_issue|
    journals = Journal.where("journalized_type = ? and journalized_id = ?","Issue",not_update_issue)
     journals.each do |journal|
#   print journal.id
#   print "\t"
#   print journal.journalized_id
#   print "\t"
#   print journal.journalized_type
#print "\n"
  end
end

##### Issue_category #####
# project_idより、抽出する。

#print "\n"
#print "# 削除するissue_categories (id,name) "
#print "\n"
 project_result_exclude.each do |not_update_project|
    issue_categories = Issue_category.where(:project_id => "#{not_update_project}")
     issue_categories.each do |issue_category|
#   print issue_category.id
#   print "\t"
#   print issue_category.name
#print "\n"
  end
end

##### Member #####
# project_idより、抽出する。

#print "\n"
#print "# 削除するmembers (id,user_id) "
#print "\n"
 project_result_exclude.each do |not_update_project|
    members = Member.where(:project_id => "#{not_update_project}")
     members.each do |member|
#   print member.id
#   print "\t"
#   print member.user_id
#print "\n"
  end
end

##### Query #####
# project_idより、抽出する。

#print "\n"
#print "# 削除するqueries (id,name) "
#print "\n"
 project_result_exclude.each do |not_update_project|
    queries = Query.where(:project_id => "#{not_update_project}")
     queries.each do |query|
#   print query.id
#   print "\t"
#   print query.name
#print "\n"
  end
end

##### Repository #####
# project_idより、抽出する。

#print "\n"
#print "# 削除するrepositories (id,url) "
#print "\n"
 project_result_exclude.each do |not_update_project|
    repositories = Repository.where(:project_id => "#{not_update_project}")
   repositories.each do |repository|
#   print repository.id
#   print "\t"
#   print repository.url
#print "\n"
  end
end

##### Time_entry #####
# project_idより、抽出する。

#print "\n"
#print "# 削除するtime_entries (id,user_id) "
#print "\n"
 project_result_exclude.each do |not_update_project|
     time_entries = Time_entry.where(:project_id => "#{not_update_project}")
     time_entries.each do |time_entry|
#   print time_entry.id
#   print "\t"
#   print time_entry.user_id
#print "\n"
  end
end

#print "\n"
#############  destroy Attachment  ################
#print "\n"


## attach_project

#print "\n"
#print "# 削除するAttachment - Project (id,filename,disk_filename)"
#print "\n"
 project_result_exclude.each do |not_update_project|
 attach_projects = Attachment.where("container_type = ? and container_id = ?", "Project",not_update_project)
    attach_projects.each do |attach_project|
#     print attach_project.id
#     print "\t"
#     print attach_project.filename
#     print "\t"
#     print attach_project.disk_filename
#    print "\n"
  attachment_disk_filename << attach_project.disk_filename
  end
end
#print "\n"
#print "\n"

## attach_issue

#print "\n"
#print "# 削除するAttachment - Issue (id,filename,disk_filename)"
#print "\n"
 issue_delete_id.each do |issue_delete_id|
  attach_issues = Attachment.where("container_type = ? and container_id = ?", "Issue",issue_delete_id) 
    attach_issues.each do |attach_issue|
#     print attach_issue.id
#     print "\t"
#     print attach_issue.filename
#     print "\t"
#     print attach_issue.disk_filename
#    print "\n"
  attachment_disk_filename << attach_issue.disk_filename
  end
end
#print "\n"
#print "\n"

## attach_version

#print "\n"
#print "# 削除するAttachment - Version (id,filename,disk_filename)"
#print "\n"
 version_delete_id.each do |version_delete_id|
 attach_versions = Attachment.where("container_type = ? and container_id = ?", "Version",version_delete_id)
    attach_versions.each do |attach_version|
#     print attach_version.id
#     print "\t"
#     print attach_version.filename
#     print "\t"
#     print attach_version.disk_filename
#    print "\n"
  attachment_disk_filename << attach_version.disk_filename
  end
end
#print "\n"
#print "\n"

## attach_document

#print "\n"
#print "# 削除するAttachment - Document (id,filename,disk_filename)"
#print "\n"
 document_delete_id.each do |document_delete_id|
 attach_documents = Attachment.where("container_type = ? and container_id = ?", "Document",document_delete_id)
    attach_documents.each do |attach_document|
#     print attach_document.id
#     print "\t"
#     print attach_document.filename
#     print "\t"
#     print attach_document.disk_filename
#    print "\n"
  attachment_disk_filename << attach_document.disk_filename
  end
end
#print "\n"
#print "\n"

## attach_wiki_page

#print "\n"
#print "# 削除するAttachment - WikiPage (id,filename,disk_filename)"
#print "\n"
 wiki_page_delete_id.each do |wiki_page_delete_id|
 attach_wiki_pages = Attachment.where("container_type = ? and container_id = ?", "WikiPage",wiki_page_delete_id)
    attach_wiki_pages.each do |attach_wiki_page|
#     print attach_wiki_page.id
#     print "\t"
#     print attach_wiki_page.filename
#     print "\t"
#     print attach_wiki_page.disk_filename
#    print "\n"
  attachment_disk_filename << attach_wiki_page.disk_filename
  end
end
#print "\n"
#print "\n"

#print attachment_disk_filename
#print "\n"

#################################
########## destroy ##############
#################################

## atachement_file ##
=begin

if cmd == "go"

  attachment_disk_filename.each do |attachment_disk_filename|
    #redmineの添付ファイルのディレクトリを指定
    delete_files = "/home/www/redmine/files/" + attachment_disk_filename     
     if delete_files == true  then
     File.unlink *delete_files
    end
    end

## news ##

 project_result_exclude.each do |not_update_project|
    newss = News.where(:project_id => "#{not_update_project}")
      newss.each do |news|
       news.destroy
      end
  end

## version ##

     version_delete_id.each do |version_delete_id|
         versions = Version.where(:id => "#{version_delete_id}")
          versions.each do |version|
          version.destroy
       end
      end

## documents ##

    document_delete_id.each do |document_delete_id|
         documents = Document.where(:id => "#{document_delete_id}")
          documents.each do |document|
          document.destroy
       end
      end


## wiki_pages ##

     wiki_page_delete_id.each do |wiki_page_delete_id|
         wiki_pages = Wiki_page.where(:id => "#{wiki_page_delete_id}")
          wiki_pages.each do |wiki_page|
          wiki_page.destroy
       end
      end

## wikis ##
 
     project_result_exclude.each do |not_update_project|
           wikis = Wiki.where(:project_id => "#{not_update_project}")
           wikis.each do |wiki|
           wiki.destroy
         end
       end

## journals ##

     issue_delete_id.each do |not_update_issue|
          journals = Journal.where("journalized_type = ? and journalized_id = ?","Issue",not_update_issue)
          journals.each do |journal|
         journal.destroy
       end
      end

## issue ##

     issue_delete_id.each do |issue_delete_id|
         issues = Issue.where(:id => "#{issue_delete_id}")
          issues.each do |issue|
          issue.destroy
       end
      end 
     
## issue_categories ##

     project_result_exclude.each do |not_update_project|
          issue_categories = Issue_category.where(:project_id => "#{not_update_project}")
          issue_categories.each do |issue_category|
          issue_category.destroy
        end
      end

## members ##

    project_result_exclude.each do |not_update_project|
          members = Member.where(:project_id => "#{not_update_project}")
          members.each do |member|
          member.destroy
        end
      end

## queries ##

    project_result_exclude.each do |not_update_project|
          queries = Query.where(:project_id => "#{not_update_project}")
          queries.each do |query|
          query.destroy
        end
      end

## repositories ##

    project_result_exclude.each do |not_update_project|
          repositories = Repository.where(:project_id => "#{not_update_project}")
          repositories.each do |repository|
          repository.destroy         
        end
      end

## time_entries ##

     project_result_exclude.each do |not_update_project|
          time_entries = Time_entry.where(:project_id => "#{not_update_project}")
          time_entries.each do |time_entry|
          time_entry.destroy
        end
      end

## project ##

     project_result_exclude.each do |not_update_project|
           projects = Project.where(:id => "#{not_update_project}") 
           projects.each do |project|
           project.destroy 
         end 
       end
  
## attachments ##
    
      attachment_disk_filename.each do |attachment_disk_filename|
           attachments = Attachment.where(:disk_filename => "#{attachment_disk_filename}")
           attachments.each do |attachment|
           attachment.destroy
        end
      end    
end

